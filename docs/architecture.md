# Rulebook Architecture

The library has four layers:

1. **Contract** — `AGENTS.md` and operating rules establish behavior and evidence standards.
2. **Rules** — focused, reusable engineering controls covering the backend lifecycle.
3. **Workflows/checklists** — procedures for recurring tasks and audit gates.
4. **Templates/examples** — structured artifacts that make planning and reporting consistent.

The system is framework-neutral. Rules describe outcomes and controls; framework modules should provide stack-specific mechanics. This keeps the core portable across Spring Boot, Node/Nest/Express, FastAPI/Django, Go, .NET, and similar stacks.

The repository intentionally separates Always-On principles from task-specific material so agents do not receive a giant undifferentiated prompt.