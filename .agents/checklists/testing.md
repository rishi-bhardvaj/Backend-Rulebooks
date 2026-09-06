# Testing Checklist

- [ ] Unit tests for core business rules
- [ ] Integration tests for persistence/infrastructure claims
- [ ] HTTP/API tests for route/wiring claims
- [ ] E2E tests for critical user journeys where appropriate
- [ ] Happy path
- [ ] Validation failure
- [ ] Authentication failure
- [ ] Authorization failure
- [ ] Not found
- [ ] Conflict
- [ ] Edge cases
- [ ] Dependency failure/timeouts where applicable
- [ ] Concurrency/duplicate execution where applicable
- [ ] Regression tests for discovered defects
- [ ] No production behavior proven only by mocks