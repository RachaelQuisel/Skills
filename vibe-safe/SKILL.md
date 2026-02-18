---
name: vibe-safe
description: Enforces security-first coding when building APIs and endpoints. Applies RAILGUARD protocol for input validation, authentication checks, rate limiting, and structured error responses. Use when creating REST APIs, route handlers, server actions, or any backend endpoint.
---

# Vibe-Safe: Secure API Development

Apply these principles when building APIs and endpoints.

## Risk-First Thinking

Before writing code:
1. **Think:** "How could this break? What would an attacker try?"
2. **Plan:** "What tests will catch that break?"
3. **Code:** Generate with security built in
4. **Verify:** Include at least one edge case test

## Non-Negotiable Constraints

- NEVER hardcode secrets — use environment variables
- NEVER use string concatenation in SQL — parameterized queries only
- NEVER expose stack traces or file paths in error responses
- ALWAYS validate ALL inputs server-side (Zod or similar)
- ALWAYS comment why when making security decisions

## Secure API Defaults

When building any endpoint, apply:
- Authentication check (unless explicitly public)
- Authorization check (user can access this resource)
- Rate limiting
- Input validation with Zod
- Structured error responses: `{ error: string, code?: string }`

## When to Read Reference

For detailed API route patterns and code examples, read `references/api-routes.md`.
