# Authentication Implementation Patterns

## Session-Based Auth (Default)

- Use `next-auth` (Auth.js) or a session library with CSRF protection built in
- Store sessions server-side (database or Redis)
- Do not use stateless JWTs for session management unless you implement token refresh and revocation
- Set session cookies with: `httpOnly: true`, `secure: true`, `sameSite: 'lax'`, reasonable `maxAge`

## Password Handling

- Hash with `bcrypt` (cost factor >= 12) or `Argon2id`
- Minimum password length: 12 characters
- Do NOT impose arbitrary complexity rules (uppercase, special chars) — they reduce usability without improving security
- Implement account lockout after 5 failed attempts with exponential backoff

## Rate Limiting on Auth Endpoints

| Endpoint | Limit |
|----------|-------|
| Login | 5 attempts per 15 min per IP + username |
| Registration | 3 accounts per hour per IP |
| Password reset | 3 requests per hour per email |

## CSRF Protection

- Use `SameSite=lax` cookies as baseline
- For state-changing forms, use CSRF tokens (most session libraries handle this)
- For API routes called from JavaScript, validate `Origin` or `Referer` header

## What NOT to Do

- Never store passwords in plaintext or with reversible encryption
- Never send passwords in URL query parameters
- Never return different error messages for "user not found" vs "wrong password"
- Never log passwords, tokens, or session IDs

## Code Pattern: Login Handler

```typescript
import { z } from "zod";
import bcrypt from "bcrypt";

const LoginSchema = z.object({
  email: z.string().email(),
  password: z.string().min(1),
});

export async function login(req: NextRequest) {
  // 1. Rate limit check
  const rateLimitResult = await checkRateLimit(req);
  if (!rateLimitResult.allowed) {
    return NextResponse.json(
      { error: "Too many attempts. Try again later." },
      { status: 429, headers: { "Retry-After": rateLimitResult.retryAfter } }
    );
  }

  // 2. Validate input
  const body = await req.json();
  const validated = LoginSchema.safeParse(body);
  if (!validated.success) {
    return NextResponse.json({ error: "Invalid credentials" }, { status: 401 });
  }

  // 3. Find user (don't reveal if user exists)
  const user = await db.user.findUnique({ where: { email: validated.data.email } });
  if (!user) {
    // Same response as wrong password
    return NextResponse.json({ error: "Invalid credentials" }, { status: 401 });
  }

  // 4. Verify password
  const valid = await bcrypt.compare(validated.data.password, user.passwordHash);
  if (!valid) {
    await recordFailedAttempt(user.id);
    return NextResponse.json({ error: "Invalid credentials" }, { status: 401 });
  }

  // 5. Create session
  const session = await createSession(user.id);

  return NextResponse.json({ success: true }, {
    headers: {
      "Set-Cookie": `session=${session.token}; HttpOnly; Secure; SameSite=Lax; Path=/`
    }
  });
}
```
