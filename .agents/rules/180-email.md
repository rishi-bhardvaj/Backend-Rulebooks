# Email

Treat email delivery as an external integration. Protect provider credentials, validate recipient input, bound retries, and make sending idempotent where business semantics require it.

Do not expose provider errors or credentials to clients. Define behavior for provider outage, timeout, bounce/rejection, duplicate sends, and asynchronous delivery. Test failure paths without sending real mail unintentionally.