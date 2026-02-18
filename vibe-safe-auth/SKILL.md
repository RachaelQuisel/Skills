---
name: vibe-safe-auth
description: Implements secure authentication patterns including login, signup, sessions, password hashing, CSRF protection, and rate limiting. Use when building auth flows, password reset, session management, or OAuth integration.
---

# Vibe-Safe: Secure Authentication

Apply these principles when implementing authentication.

## Risk-First Thinking

Before writing auth code:
1. **Think:** "How could an attacker bypass this?"
2. **Plan:** "What tests catch auth failures?"
3. **Code:** Generate with security built in
4. **Verify:** Test both happy path and attack scenarios

## Non-Negotiable Constraints

- NEVER store passwords in plaintext or with reversible encryption
- NEVER send passwords in URL query parameters
- NEVER log passwords, tokens, or session IDs
- NEVER return different errors for "user not found" vs "wrong password"
- ALWAYS use bcrypt (cost >= 12) or Argon2id for password hashing
- ALWAYS use generic error: "Invalid credentials"

## Secure Auth Defaults

When building login/signup:
- Session-based auth with CSRF protection
- Rate limiting: 5 attempts per 15 min per IP+username
- Account lockout after failed attempts
- Secure cookies: `httpOnly`, `secure`, `sameSite: 'lax'`

## When to Read Reference

For detailed auth implementation patterns, read `references/auth.md`.
