# Verification Example: Protected Resource

Assume `GET /api/private/resource` requires an authenticated owner.

1. Start the actual application with a test database.
2. Authenticate User A and capture a valid token from the real login endpoint.
3. Call the resource without a token → expect 401.
4. Call with a malformed/invalid token → expect 401.
5. Call with User A's valid token for User A's resource → expect documented 2xx.
6. Call User B's private resource with User A's token → expect 403 or policy-defined 404.
7. Verify the database and logs show no unauthorized mutation or secret leakage.
8. Repeat through automated API/integration tests.

The example is evidence-driven: expected results are not evidence until the running system produces them.