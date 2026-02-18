# Secure File Upload Patterns

## Validation

- Validate MIME type on server — never trust client-provided `Content-Type`
- Use a library like `file-type` to detect actual file type from magic bytes
- Enforce file size limits (e.g., 10 MB for images, 50 MB for documents)
- Reject before fully buffering the file
- Reject dangerous extensions: `.exe`, `.bat`, `.sh`, `.php`, `.jsp`, `.html`, `.svg` (can contain scripts)

## Storage

- Never store uploaded files in the webroot or any publicly accessible directory
- Use cloud storage (S3, GCS, R2) with pre-signed URLs for access control
- Generate random filenames on upload — never use original filename as storage key
- Store file metadata (original name, uploader, timestamp, size, MIME type) in database

## Processing

- Resize and re-encode images server-side to strip EXIF metadata and potential embedded payloads
- Process files asynchronously (queue) for large files or virus scanning
- Scan for malware if handling files from untrusted users

## Access Control

- Use pre-signed URLs with short expiration (15 minutes)
- Verify requesting user has permission to access the file before generating download URL
- Implement download rate limiting to prevent abuse

## Code Pattern: Upload Handler

```typescript
import { fileTypeFromBuffer } from "file-type";
import { randomUUID } from "crypto";
import { S3Client, PutObjectCommand } from "@aws-sdk/client-s3";

const ALLOWED_TYPES = ["image/jpeg", "image/png", "image/webp"];
const MAX_SIZE = 10 * 1024 * 1024; // 10MB

export async function uploadHandler(req: NextRequest) {
  // 1. Auth check
  const session = await auth();
  if (!session) {
    return NextResponse.json({ error: "Unauthorized" }, { status: 401 });
  }

  // 2. Get file from form data
  const formData = await req.formData();
  const file = formData.get("file") as File;

  if (!file) {
    return NextResponse.json({ error: "No file provided" }, { status: 400 });
  }

  // 3. Check size before buffering fully
  if (file.size > MAX_SIZE) {
    return NextResponse.json({ error: "File too large" }, { status: 400 });
  }

  // 4. Validate MIME from magic bytes
  const buffer = Buffer.from(await file.arrayBuffer());
  const fileType = await fileTypeFromBuffer(buffer);

  if (!fileType || !ALLOWED_TYPES.includes(fileType.mime)) {
    return NextResponse.json({ error: "Invalid file type" }, { status: 400 });
  }

  // 5. Generate random filename
  const key = `uploads/${randomUUID()}.${fileType.ext}`;

  // 6. Upload to S3
  await s3.send(new PutObjectCommand({
    Bucket: process.env.S3_BUCKET,
    Key: key,
    Body: buffer,
    ContentType: fileType.mime,
  }));

  // 7. Store metadata in database
  await db.file.create({
    data: {
      key,
      originalName: file.name,
      mimeType: fileType.mime,
      size: file.size,
      uploadedBy: session.user.id,
    },
  });

  return NextResponse.json({ key });
}
```
