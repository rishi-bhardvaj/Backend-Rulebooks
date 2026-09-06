# Runtime Verification Rules

Do not prove an integration by reading code alone. Start the relevant application/service and use its real boundary whenever practical.

Record exact commands, inputs, observed outputs/statuses, and environment assumptions. Verify route registration, middleware ordering, persistence, and external calls rather than testing isolated methods only.

When a runtime dependency cannot be started, explicitly mark the affected behavior NOT VERIFIED or BLOCKED.