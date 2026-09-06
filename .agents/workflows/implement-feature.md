# Workflow: Implement Feature

**Inspect → Plan → Implement → Build → Run → Test → Verify → Audit → Report.**

Translate acceptance criteria into executable checks. Trace affected route/service/repository/integration paths before coding. Implement the smallest coherent change. Run focused tests, then real runtime/API checks for integration claims. Exercise failure and authorization boundaries. Search for disconnected routes, hardcoded data, mocks in production paths, TODO/FIXME bypasses, incorrect environment variables, and swallowed errors. Fix root causes and rerun regression checks.