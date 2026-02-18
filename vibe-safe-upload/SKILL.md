---
name: vibe-safe-upload
description: Implements secure file upload handling with MIME validation, size limits, safe storage, and access control. Use when building image uploads, document uploads, media handling, or any user-submitted file processing.
---

# Vibe-Safe: Secure File Uploads

Apply these principles when handling file uploads.

## Risk-First Thinking

Before writing upload code:
1. **Think:** "What malicious files could be uploaded?"
2. **Plan:** "How do I validate before storing?"
3. **Code:** Generate with security built in
4. **Verify:** Test with malicious file types

## Non-Negotiable Constraints

- NEVER store uploads in the webroot or publicly accessible directories
- NEVER trust client-provided Content-Type or filename
- NEVER use original filenames as storage keys
- ALWAYS validate MIME type from file magic bytes
- ALWAYS enforce size limits before buffering

## Secure Upload Defaults

When building file uploads:
- Validate MIME from magic bytes (use `file-type` library)
- Enforce size limits (e.g., 10MB images, 50MB docs)
- Store in cloud storage (S3, R2, GCS)
- Generate random filenames
- Use pre-signed URLs with short expiration

## When to Read Reference

For detailed file upload patterns, read `references/file-upload.md`.
