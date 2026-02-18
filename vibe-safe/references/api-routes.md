# API Route Security Patterns

## Request Handling

- Validate ALL request bodies, query params, and route params with Zod schemas before processing
- Return structured JSON error responses: `{ error: string, code?: string }`
- Never return raw error messages or stack traces

## Status Codes

- 400: Validation errors
- 401: Unauthenticated
- 403: Unauthorized (authenticated but not permitted)
- 404: Not found
- 429: Rate limited
- 500: Server errors

## Authentication & Authorization

- Check authentication on every non-public endpoint
- Verify session or token validity before processing
- Implement authorization: verify user has permission to access the resource
- Never trust client-provided user IDs — derive identity from session/token

## Rate Limiting

- Apply to all public-facing endpoints, especially auth endpoints
- Use sliding window rate limiting
- Return `429 Too Many Requests` with `Retry-After` header
- Stricter limits on sensitive endpoints (login, password reset)

## Response Security

- Never return internal IDs, database column names, or implementation details
- Set `Cache-Control: no-store` on user-specific or sensitive data
- Always implement pagination with maximum page size for list endpoints

## Code Pattern

```typescript
import { NextRequest, NextResponse } from "next/server";
import { z } from "zod";

const RequestSchema = z.object({
  // define your schema
});

export async function POST(req: NextRequest) {
  try {
    // 1. Auth check
    const session = await auth();
    if (!session) {
      return NextResponse.json({ error: "Unauthorized" }, { status: 401 });
    }

    // 2. Validate input
    const body = await req.json();
    const validated = RequestSchema.safeParse(body);
    if (!validated.success) {
      return NextResponse.json(
        { error: "Invalid request", code: "VALIDATION_ERROR" },
        { status: 400 }
      );
    }

    // 3. Business logic
    // ...

    // 4. Return structured response
    return NextResponse.json({ data: result });
  } catch (error) {
    logger.error("API error", { error, path: req.nextUrl.pathname });
    return NextResponse.json(
      { error: "Internal server error" },
      { status: 500 }
    );
  }
}
```
