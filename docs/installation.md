# Installation

## Into an application repository

Copy `AGENTS.md` and `.agents/` into the target repository. Commit them when the team wants shared agent behavior.

Then instruct the coding agent to read `AGENTS.md` before editing and to load the specialized rule/workflow files relevant to the task.

## Antigravity

Use `.agents/rules/` as the primary rules directory. Configure the host so the operating contract is always available and specialized modules are selected for relevant tasks. See `docs/antigravity.md`.

## Adapting to a stack

Keep the core modules unchanged where possible. Add a stack-specific directory/module that translates commands, test frameworks, configuration, and runtime tooling into the same verification obligations.

## Verification

After installation, ask the agent to perform a small audit and produce a verification report. The rulebook itself should not be considered effective merely because its files exist.