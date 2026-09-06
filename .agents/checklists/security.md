# Security Checklist

- [ ] Threat/trust boundaries identified
- [ ] AuthN/AuthZ verified
- [ ] IDOR/tenant isolation tested
- [ ] Input validation and output handling reviewed
- [ ] Injection/command/path traversal risks reviewed
- [ ] SSRF reviewed where URLs are accepted
- [ ] File upload controls reviewed
- [ ] CSRF/XSS reviewed where applicable
- [ ] CORS and security headers reviewed
- [ ] Rate limiting/brute-force protection reviewed
- [ ] Secrets absent from source/logs
- [ ] Cookies/session security reviewed
- [ ] Dependency/security scanning performed where available
- [ ] Errors do not leak internals
- [ ] Development bypasses absent
- [ ] Findings have evidence and remediation status