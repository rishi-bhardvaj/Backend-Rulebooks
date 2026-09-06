# Configuration Handoff Audit

**Severity: HIGH**  
**Activation:** Model Decision whenever a task adds or changes an external integration or runtime configuration.

Before completion, audit every newly introduced required value.

## Audit each value

Record:

| Value | Exact repository/deployment location | Variable/config key | Environment | Server/client exposure | Source | Verification |
| --- | --- | --- | --- | --- | --- | --- |
| Provider credential/config | actual path or deployment setting | exact name | local/test/staging/prod | server-only or client-safe | where developer obtains it | actual command/test |

The path and key must come from the inspected repository or deployment configuration. Never invent a conventional location.

## Required checks

- local configuration path identified
- safe example configuration updated when appropriate
- CI/test secret location identified when needed
- staging/production secret location identified when needed
- restart/reload requirement stated when applicable
- missing configuration fails clearly rather than producing fake success
- server secrets are never exposed to browser/client configuration
- no secret is printed in logs, source, tests, fixtures, commits, or reports
- real integration verification performed when credentials/services are available

## Completion rule

A task that requires developer-supplied configuration cannot be marked `VERIFIED` unless the relevant integration was actually exercised, or the repository has a justified alternative verification boundary. Otherwise report `NOT VERIFIED` or `BLOCKED` with the exact missing configuration and where it belongs.
