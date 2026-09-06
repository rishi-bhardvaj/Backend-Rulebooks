# Authentication

**CRITICAL:** Authentication is server-side. A login screen, client flag, generated JWT, or stored token is not proof of authentication.

Implement and verify as applicable: registration, password hashing/verification, login, logout, access tokens, refresh tokens, expiry, rotation/revocation, sessions, password reset, email verification, account disablement, brute-force controls, and rate limiting.

For JWTs validate signature, explicit allowed algorithms, expiry, required claims, and issuer/audience when configured. Use secure key storage and a rotation strategy. Never accept unsigned tokens, algorithm confusion, expired tokens, or client-created identity claims.

Minimum runtime matrix: wrong password → reject; unknown user → reject; no token → reject protected endpoint; malformed/invalid token → reject; expired token → reject; valid token → succeed when authorized; revoked/rotated token → reject when policy requires.