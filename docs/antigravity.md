# Google Antigravity Integration

Use this repository as a portable engineering policy layer rather than assuming a Claude Code-specific instruction mechanism.

## Recommended layout

For current Antigravity workspaces, place rules under `.agents/rules/` and keep `AGENTS.md` at repository root as the master contract. If an environment expects `.agent/rules/`, the same modules can be copied there.

Keep individual rules focused. Antigravity rules can be configured as Always On, Manual, Model Decision, or Glob activated. Recommended policy:

- Always On: `00-operating-contract.md`, security/verification principles, and evidence rules.
- Model Decision: architecture, API, database, observability, performance.
- Manual: specialized workflows such as auth audit, webhook, file storage, production audit.
- Glob: framework-specific or file-type-specific rules when the project supports them.

Do not assume that another agent's tool commands, context files, or lifecycle hooks exist. State the engineering outcome and verification requirement; let the host agent map it to its available tools.

## Stack adaptation

The core rules intentionally avoid framework-specific APIs. Add optional modules for Spring Boot, Node/Nest/Express, FastAPI/Django, Go, .NET, or other stacks. A framework module must explain how to perform the same verification gates in that stack rather than weakening the gates.

## Operating instruction

Tell the agent: read `AGENTS.md`, inspect the repository, then read only the specialized rules applicable to the task. Never declare completion without the evidence contract.