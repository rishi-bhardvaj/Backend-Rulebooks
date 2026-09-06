# Observability

Provide structured logs, request/correlation IDs, health/readiness/liveness signals, metrics/error tracking where appropriate, audit/security events, and graceful shutdown.

Diagnostic context should let an operator trace request → identity/auth decision → business operation → persistence/external dependency → response without logging secrets, credentials, tokens, or sensitive payloads.

Verify health endpoints represent real dependency readiness rather than process liveness alone where required.