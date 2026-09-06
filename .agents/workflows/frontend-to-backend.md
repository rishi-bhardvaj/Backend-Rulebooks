# Workflow: Frontend Context → Backend Implementation

Use this workflow when frontend code/context is supplied and the goal is to make or complete the backend behind it.

## Phase 1 — Inventory

1. Read repository rules and inspect the backend repository.
2. Inspect the supplied frontend context systematically.
3. Enumerate user-visible flows and state transitions.
4. Extract every observed API/event/storage dependency.
5. Identify authentication, authorization, ownership, and tenant assumptions.

## Phase 2 — Contract map

Create a table or equivalent artifact with:

`Frontend source | Action | Backend capability | Method/path/event | Request | Response | Data model | Auth | Authorization | Validation | Errors | Tests | Fixtures`

Mark each item `OBSERVED`, `INFERRED`, `ASSUMED`, or `MISSING`.

## Phase 3 — Backend gap analysis

For every frontend dependency classify it as:

- implemented and compatible;
- implemented but contract-incompatible;
- partially implemented;
- missing;
- blocked by an environment/integration dependency.

Do not duplicate existing domain logic merely to satisfy a frontend call.

## Phase 4 — Implementation

Implement the smallest complete backend slice required by the observed frontend behavior. Include persistence, validation, authentication, authorization, error semantics, and observability where applicable.

Do not weaken backend security because the frontend assumes a restriction.

## Phase 5 — Dummy data

Generate deterministic test fixtures for the discovered entities and flows. Include successful, empty, boundary, invalid, unauthorized, forbidden, ownership/tenant-isolation, duplicate/conflict, and relevant lifecycle states.

Seed the test environment only; never seed production with dummy credentials or data.

## Phase 6 — Real verification

1. Build/compile.
2. Start the real backend and required local dependencies where practical.
3. Call the actual HTTP/event boundary using request shapes extracted from the frontend.
4. Verify response shape, status codes, persistence, authorization, and side effects.
5. Run automated tests against the fixture data.
6. Exercise negative/security cases.
7. If possible, connect the frontend to the backend and execute the actual user flow.

## Phase 7 — Diagnose

If the frontend flow fails, trace the complete chain:

`UI action → frontend client → network request → route → middleware → controller/handler → service/domain → database/external integration → response → frontend state`

Fix the earliest root cause rather than adding a frontend/backend workaround.

## Phase 8 — Report

Report:

- frontend capabilities discovered;
- backend endpoints/contracts implemented or changed;
- data models/migrations changed;
- fixtures created;
- tests executed and exact results;
- real runtime flows verified;
- security/negative cases verified;
- remaining `NOT VERIFIED` or `BLOCKED` items;
- assumptions and inferred requirements.
