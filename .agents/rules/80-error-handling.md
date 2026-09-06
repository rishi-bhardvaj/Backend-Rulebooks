# Error Handling

Define a consistent, machine-readable error contract. Map expected domain failures to deliberate HTTP/event outcomes and preserve unexpected failures as failures.

Never swallow exceptions, log-and-return-success, or expose passwords, tokens, secrets, SQL, stack traces, or infrastructure details. Logs may contain diagnostic context only when safely redacted.

Test not-found, validation, conflict, dependency failure, timeout, database failure, and unexpected exception paths. Verify that failed operations do not create partial or misleading success state.