# Validation

Treat request bodies, query/path parameters, headers, files, webhooks, and external responses as untrusted. Validate at the server boundary with explicit schemas and domain constraints.

Reject malformed, missing, excessive, contradictory, and out-of-range inputs. Do not rely on frontend validation. Normalize only where the contract permits it.

Test validation failures through the real boundary and ensure invalid input cannot trigger unintended database writes, privileged operations, or resource exhaustion.