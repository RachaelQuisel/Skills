# Debugging & Error Research

## Research Checklist

1. **Capture the full error** - Stack trace, error code, context
2. **Identify error type** - Syntax, runtime, logic, network
3. **Search for exact error message** - Often solved before
4. **Check recent changes** - What changed before it broke?
5. **Isolate the problem** - Minimal reproduction

## Error Categories

### Network/API Errors
- 400: Bad request - check payload format
- 401/403: Auth issues - verify credentials
- 404: Wrong endpoint or resource doesn't exist
- 429: Rate limited - add delays
- 500: Server error - check server logs

### Code Errors
- TypeError: Wrong data type passed
- ReferenceError: Variable not defined
- SyntaxError: Parse the exact line/character

### Platform-Specific (Wix, n8n, etc.)
- Check platform-specific error codes
- Review platform documentation
- Search community forums

## Subagent Prompts

```
"[exact error message] solution"
"[platform] [error code] fix"
"[language] [error type] common causes"
```

## Debugging Workflow

1. **Reproduce** - Can you trigger it consistently?
2. **Isolate** - Remove code until error stops
3. **Inspect** - Log values at key points
4. **Fix** - Make minimal change
5. **Verify** - Confirm fix, check for side effects

## Output Template

```
## Error Analysis
- Error: [exact message]
- Type: [category]
- Location: [file:line]

## Root Cause
[What's actually wrong]

## Solution
[Step-by-step fix]

## Prevention
[How to avoid in future]
```
