# Error Handling Patterns

## Server-Side (API Routes & Server Actions)

- Wrap all async operations in try/catch
- Log the full error internally with context (path, method, user ID)
- Return a sanitized error to the client — never expose stack traces, file paths, or dependency versions
- Use structured error responses: `{ error: string, code?: string, details?: object }`
- Differentiate operational errors (expected: validation, not found) from programmer errors (unexpected: null reference)

## Client-Side (React)

- Implement `error.tsx` boundaries in each major route segment
- Use `global-error.tsx` at root layout for catastrophic failures
- Display user-friendly error messages with retry actions
- Log client-side errors to monitoring service (Sentry, LogRocket)

## Custom Error Classes

```typescript
export class AppError extends Error {
  constructor(
    message: string,
    public statusCode: number = 500,
    public code?: string,
    public isOperational: boolean = true
  ) {
    super(message);
    this.name = "AppError";
  }
}

// Usage
throw new AppError("User not found", 404, "USER_NOT_FOUND");
throw new AppError("Rate limit exceeded", 429, "RATE_LIMITED");
```

## What NOT to Do

- Never catch an error and silently swallow it without logging
- Never use `catch (e: any)` — use `catch (error: unknown)` and narrow the type
- Never return `200 OK` with an error body — use appropriate HTTP status codes

## Code Pattern: API Error Handler

```typescript
import { NextRequest, NextResponse } from "next/server";
import { logger } from "@/lib/logger";
import { AppError } from "@/lib/errors";

export async function handleApiRequest(
  req: NextRequest,
  handler: () => Promise<NextResponse>
) {
  try {
    return await handler();
  } catch (error) {
    // Log full error internally
    logger.error("API error", {
      error,
      path: req.nextUrl.pathname,
      method: req.method,
    });

    // Return sanitized error to client
    if (error instanceof AppError && error.isOperational) {
      return NextResponse.json(
        { error: error.message, code: error.code },
        { status: error.statusCode }
      );
    }

    // Unknown errors get generic response
    return NextResponse.json(
      { error: "Internal server error" },
      { status: 500 }
    );
  }
}
```

## React Error Boundary Pattern

```typescript
// app/error.tsx
"use client";

export default function Error({
  error,
  reset,
}: {
  error: Error & { digest?: string };
  reset: () => void;
}) {
  useEffect(() => {
    // Log to error reporting service
    captureException(error);
  }, [error]);

  return (
    <div>
      <h2>Something went wrong</h2>
      <button onClick={reset}>Try again</button>
    </div>
  );
}
```
