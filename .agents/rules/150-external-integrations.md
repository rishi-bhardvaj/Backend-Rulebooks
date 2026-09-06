# External Integrations

Validate configuration and external responses. Set bounded timeouts; use bounded retries and exponential backoff only where safe; honor rate limits; handle partial failures; protect credentials; and implement idempotency where required.

Do not turn upstream errors into fake success. Test timeout, malformed response, authentication failure, rate limiting, unavailable dependency, retry exhaustion, and duplicate requests. Log failures safely without credentials or sensitive payloads.