# Architecture

Inspect the existing dependency graph before introducing abstractions. Preserve clear boundaries between transport/controllers, application/services, domain/business rules, persistence, infrastructure, and configuration where the stack supports them.

Every new component must have a real caller and a clear responsibility. Trace one representative request end-to-end before declaring integration complete: entry point → routing/middleware → auth → application logic → persistence/external service → response.

Avoid speculative layers, broad rewrites, circular dependencies, and duplicate business rules. Architectural decisions that affect public contracts or data ownership must be documented.