# Webhooks

Verify provider signatures using the documented canonical representation and constant-time comparison where appropriate. Validate timestamps/replay windows when supported. Treat deliveries as untrusted and potentially duplicated.

Use idempotency keys/event IDs to prevent duplicate effects. Validate payloads, bound processing, and define retry/failure semantics. Never log secrets or full sensitive payloads unnecessarily. Test invalid signatures, replay, duplicates, malformed payloads, and downstream failure.