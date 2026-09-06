# Workflow: Authentication

1. Identify identity model, session/token model, secret/key configuration, and protected routes.
2. Implement server-side credential verification and secure password hashing.
3. Implement token/session validation, expiry, rotation/revocation as required.
4. Protect routes through actual middleware/security filters.
5. Run the application.
6. Verify wrong password, unknown user, no token, malformed/invalid token, expired token, valid token, and revoked token where applicable.
7. Inspect logs/configuration for secrets and bypasses.
8. Add regression tests and report actual evidence.