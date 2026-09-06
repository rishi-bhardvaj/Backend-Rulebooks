# API Design

For each endpoint define method, path, auth requirement, authorization rule, request schema, validation, success status/body, error contract, pagination/filter/sort behavior, idempotency, and concurrency semantics where applicable.

Register routes in the actual application. Test through the real HTTP stack when practical; do not infer registration from controller existence. Verify frontend base URLs, content types, credentials, headers, response parsing, and error handling when a client exists.

Use status codes consistently. Never return 2xx for an operation that failed. Avoid leaking implementation details in error responses.