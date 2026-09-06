# Workflow: Broken Backend Audit

Investigate in order: 1) structure, 2) build, 3) configuration, 4) runtime startup, 5) database, 6) routes, 7) authentication, 8) authorization, 9) business logic, 10) frontend integration, 11) external integrations, 12) tests, 13) security, 14) production readiness.

Reproduce the failure before patching. If login succeeds with invalid credentials, classify authentication as BROKEN until a server-side negative test disproves the finding. Inspect logs and actual network/database behavior. Fix root causes, add regression tests, rerun the full relevant verification matrix.