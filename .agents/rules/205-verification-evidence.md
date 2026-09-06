# Verification Evidence Contract

**Severity: CRITICAL**  
**Activation:** Always On for implementation, integration, debugging, and completion reports.

A backend task is not complete because code exists or a build succeeds. Completion requires evidence appropriate to the boundary changed.

## Evidence ladder

Record the strongest evidence actually obtained:

1. **Static evidence** — inspected code/config/types/schema; useful for structure but not proof of runtime behavior.
2. **Build evidence** — compile/typecheck/build succeeded; proves only that the invoked build gate passed.
3. **Automated test evidence** — relevant unit/component/integration/E2E tests passed.
4. **Runtime boundary evidence** — started the service and exercised the real HTTP/RPC/event/queue/webhook boundary.
5. **Persistence/integration evidence** — verified database state or external side effect with a real configured dependency.
6. **Negative/security evidence** — unauthorized, forbidden, invalid, duplicate, expired, cross-owner/tenant, or other relevant failure paths were exercised.

Do not claim a stronger level from weaker evidence.

## Required report fields

For meaningful backend work report:

- commands actually run
- endpoint/job/event exercised
- request identity/auth context used
- observed response/status/result
- persistence or external side effect checked
- negative/security cases checked
- failures encountered and diagnosis
- configuration/credentials required but unavailable
- final status: `IMPLEMENTED`, `VERIFIED`, `NOT VERIFIED`, or `BLOCKED`

## Anti-fabrication

Never invent command output, HTTP status codes, logs, database rows, queue delivery, third-party responses, or successful deployment. If a service could not be started or a credential was unavailable, say so and downgrade the completion state.
