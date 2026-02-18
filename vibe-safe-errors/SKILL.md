---
name: vibe-safe-errors
description: Implements secure error handling patterns that log internally but never leak sensitive information to clients. Use when adding try/catch blocks, error boundaries, creating error responses, or building error handling middleware.
---

# Vibe-Safe: Secure Error Handling

Apply these principles when handling errors.

## Risk-First Thinking

Before writing error handling:
1. **Think:** "What information could leak to attackers?"
2. **Plan:** "What gets logged vs returned?"
3. **Code:** Generate with security built in
4. **Verify:** Test that errors don't expose internals

## Non-Negotiable Constraints

- NEVER return stack traces to clients
- NEVER expose file paths, dependency versions, or database details
- NEVER silently swallow errors without logging
- NEVER use `catch (e: any)` — use `catch (error: unknown)`
- ALWAYS log full error internally with context
- ALWAYS return sanitized, generic errors to clients

## Secure Error Defaults

When handling errors:
- Wrap all async operations in try/catch
- Log internally: full error, path, method, user ID
- Return to client: generic message, error code, appropriate status
- Use structured responses: `{ error: string, code?: string }`

## When to Read Reference

For detailed error handling patterns, read `references/error-handling.md`.
