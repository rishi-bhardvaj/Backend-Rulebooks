# Workflow: Security Audit

Inventory trust boundaries and privileged operations. Review authentication, authorization/IDOR, tenant isolation, input validation, injection, SSRF, file handling, CSRF/XSS where applicable, CORS/headers, secrets, sessions/cookies, rate limits, dependency vulnerabilities, logs, and error exposure.

Search for auth skips, development bypasses, client-trusted roles/IDs, hardcoded credentials, unsafe deserialization/commands, path traversal, and production mocks. Verify findings with tests where safe. Record severity, exploit precondition, impact, evidence, remediation, and residual risk.