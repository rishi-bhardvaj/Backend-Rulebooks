# File Storage

Treat uploads as hostile input. Enforce size/count limits, validate content type using trusted inspection where appropriate, sanitize names, isolate storage permissions, and prevent path traversal. Use signed URLs for controlled object access where appropriate.

Define ownership, retention, deletion, orphan cleanup, and malware scanning requirements for the threat model. Test oversized, malformed, mislabeled, unauthorized, and duplicate uploads.