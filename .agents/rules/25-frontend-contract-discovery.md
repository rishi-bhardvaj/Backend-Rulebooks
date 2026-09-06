# Frontend Contract Discovery

**Severity:** CRITICAL
**Activation:** Model Decision; apply whenever frontend source, screenshots, generated UI, design exports, API clients, route definitions, forms, or frontend context is supplied.

## Objective

Treat the frontend as a source of observable product requirements, not as authority over backend security. Reverse-engineer the backend contract required to make the supplied frontend functional.

## Required analysis

Before implementing backend behavior, inspect the supplied frontend context for:

- pages, routes, screens, dialogs, drawers, forms, tables, filters, pagination, search, sorting, uploads, downloads, dashboards, notifications, and state transitions;
- network/API clients, fetch/axios wrappers, query hooks, mutations, GraphQL operations, WebSocket/SSE usage, generated clients, and hardcoded URLs;
- request methods, paths, headers, query parameters, path parameters, request bodies, multipart fields, cookies/tokens, response shapes, status-code handling, retries, polling, and optimistic updates;
- entities, fields, enums, relationships, IDs, timestamps, nullable/optional fields, validation messages, loading/empty/error states, and derived values;
- authentication flows, role/permission checks, tenant/workspace/project boundaries, and ownership assumptions visible in the client;
- integration points such as email, payments, storage, maps, search, analytics, queues, or third-party APIs.

## Produce a frontend-to-backend contract

Create an explicit inventory before coding. For every discovered backend dependency record:

`frontend location → user action → backend capability → HTTP/event boundary → request contract → response contract → persistence/domain behavior → authorization → validation → failure cases → tests → fixture data`

Separate:

- **Observed:** directly supported by frontend code/context.
- **Inferred:** necessary to connect observed behavior.
- **Assumed:** ambiguous behavior chosen for implementation.
- **Missing:** required information that cannot be established from context.

Do not silently turn an assumption into a requirement.

## Contract reconciliation

If the frontend expects an endpoint that does not exist, specify the backend implementation required. If an endpoint exists but its request/response contract differs, identify the mismatch and implement the smallest coherent correction. If the frontend contains a client-side security check, do not treat it as authorization; enforce the boundary server-side.

When a feature is represented only visually and no API contract exists, infer only what is necessary and document the inference. Do not invent unrelated backend capabilities.

## Verification

After implementation, exercise the real backend through the same boundary the frontend uses. Prefer an automated contract/integration test that proves the frontend-request shape is accepted and the response shape satisfies the observed client expectations.

A frontend can render successfully with fake data while the backend is broken. Rendering is therefore not evidence of backend completion.
