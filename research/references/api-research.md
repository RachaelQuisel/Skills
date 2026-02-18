# API & Integration Research

## Research Checklist

1. **Find official documentation** - Always start with official API docs
2. **Identify authentication method** - API keys, OAuth, tokens
3. **Check rate limits** - Requests per minute/hour
4. **Find code examples** - Official SDKs or community examples
5. **Look for webhooks** - Real-time vs polling options

## Common Integration Patterns

### REST APIs
- Check for OpenAPI/Swagger specs
- Note base URL and versioning
- Identify required headers

### Webhooks
- Payload format (JSON structure)
- Verification/signature methods
- Retry behavior

### No-Code Platforms (n8n, Make, Zapier)
- Check for native connectors first
- HTTP Request node as fallback
- Authentication setup requirements

## Subagent Prompts

Deploy these searches in parallel:

```
"[Platform] API documentation authentication"
"[Platform] API rate limits and quotas"
"[Platform] webhook setup guide"
"[Platform] [OtherPlatform] integration example"
```

## Output Template

```
## API Overview
- Base URL:
- Auth method:
- Rate limits:

## Key Endpoints
1. [Endpoint] - [Purpose]
2. [Endpoint] - [Purpose]

## Integration Approach
[Recommended method with reasoning]

## Code Example
[Working code snippet]
```
