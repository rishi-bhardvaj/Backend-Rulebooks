# Test Data and Fixture Engineering

**Severity:** CRITICAL for features requiring persistence or realistic integration testing
**Activation:** Model Decision; apply when implementing, verifying, or debugging behavior that needs data.

## Objective

Create deterministic, realistic dummy data so backend behavior can be tested without depending on production data or manually prepared state.

## Rules

- Test data must be clearly non-production and contain no real credentials, access tokens, private keys, payment secrets, or unnecessary personal data.
- Prefer deterministic factories/builders/fixtures over ad-hoc records scattered through tests.
- Generate data that exercises normal, boundary, empty, invalid, unauthorized, forbidden, duplicate, missing, and conflicting cases where applicable.
- Respect real database constraints, foreign keys, unique indexes, enums, required fields, lifecycle states, tenant boundaries, and ownership relationships.
- Create fixtures for every important actor/role and at least two ownership/tenant contexts when authorization is relevant.
- Include relationships required by the frontend flows discovered during frontend contract analysis.
- Use stable identifiers only where tests need them; otherwise generate isolated IDs.
- Fixtures must be safe to reset, seed, or run repeatedly. Avoid tests that depend on execution order.
- Do not use a fixture to conceal a broken integration. If the real feature requires an external service, use a controlled test integration or explicitly scoped test double and verify the production path separately.

## Required fixture categories

For a feature, consider generating:

1. happy-path records;
2. empty-state records;
3. boundary-size/length records;
4. invalid-input cases;
5. unauthorized user records;
6. authenticated-but-forbidden records;
7. cross-tenant/cross-owner records;
8. duplicate/conflict records;
9. deleted/archived/inactive records;
10. records representing each relevant enum/status/state.

## Deliverables

When practical, add:

- a reusable test-data factory or fixture module;
- a seed/reset mechanism appropriate to the project's test environment;
- integration/API tests that consume the fixtures;
- a short fixture README explaining how to seed/reset and what scenarios are represented.

Never claim fixture-backed tests passed unless they were actually executed.
