# Definition of Done

A feature is DONE only when every applicable gate is satisfied with evidence.

- [ ] Requirements/assumptions explicit
- [ ] Architecture/integration path inspected
- [ ] Code implemented and registered
- [ ] Build passes
- [ ] Application runs
- [ ] Real API/event boundary verified
- [ ] Database persistence/migrations verified
- [ ] Authentication verified
- [ ] Authorization/ownership/tenant boundaries verified
- [ ] Validation and error paths verified
- [ ] Happy + negative + edge tests pass
- [ ] Regression suite relevant to change passes
- [ ] Security audit complete
- [ ] Observability/configuration reviewed
- [ ] External integrations verified or explicitly blocked
- [ ] Deployment/production readiness reviewed
- [ ] No accidental production mocks/bypasses/secrets
- [ ] Evidence report completed

If a required gate cannot be executed: mark `NOT VERIFIED` or `BLOCKED`; never infer success.