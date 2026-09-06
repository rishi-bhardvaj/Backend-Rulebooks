# Background Jobs

Jobs must tolerate retries and duplicate execution. Define idempotency, retry limits, backoff, dead-letter/failure handling, visibility/monitoring, scheduling semantics, and graceful shutdown.

Persist durable state before acknowledging work where required. Do not assume process memory survives restarts. Test duplicate delivery, transient failure, permanent failure, cancellation, and shutdown behavior.