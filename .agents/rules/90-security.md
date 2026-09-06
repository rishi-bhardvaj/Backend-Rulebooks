# Security

Apply least privilege, fail-closed behavior, defense in depth, and explicit trust boundaries. Review applicable OWASP risks: broken access control/IDOR, injection, XSS, CSRF, SSRF, path traversal, command injection, unsafe deserialization, file upload abuse, secret exposure, CORS, security headers, rate limiting, dependency vulnerabilities, session/cookie weaknesses, and sensitive-data leakage.

**CRITICAL:** no hardcoded secrets; no auth bypass; no client-controlled authorization; no insecure development bypass; no disabling security controls to satisfy tests.

Security-sensitive changes require negative tests and an audit of logs, configuration, dependencies, and failure behavior.