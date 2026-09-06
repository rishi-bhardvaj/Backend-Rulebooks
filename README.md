# Backend Rulebooks

A reusable, stack-agnostic engineering rulebook for AI coding agents building real backends.

## Purpose

This repository exists to prevent agents from confusing source-code presence with working software. The governing loop is:

**UNDERSTAND → PLAN → IMPLEMENT → BUILD → RUN → TEST → VERIFY → DIAGNOSE → FIX → RETEST → AUDIT → REPORT**

A feature is not complete because it compiles, a UI renders, an endpoint exists, or a JWT can be generated. Completion requires executable evidence for the applicable behavior and security boundaries.

## Antigravity

Google Antigravity workspace rules are Markdown files under `.agents/rules/` (with backward compatibility for `.agent/rules`). Rules can be Always On, Manual, Model Decision, or Glob activated. Each rule file is limited to 12,000 characters. This repository therefore keeps rules modular and short enough to compose. See `docs/antigravity.md`.

## Installation

Copy the `.agents/`, `AGENTS.md`, and relevant workflow/checklist/template files into the application repository. Keep the framework-neutral core rules enabled and add stack-specific rules only where applicable.

For Antigravity, prefer `.agents/rules/`. The legacy `.agent/rules/` layout is retained as a compatibility option, not as the primary layout.

## Severity

- **CRITICAL** — must not be silently violated; completion is blocked until resolved or explicitly accepted as a documented blocker.
- **WARNING** — requires investigation and either remediation or documented rationale.
- **ADVISORY** — recommended engineering practice.

## Evidence states

Agents must distinguish **IMPLEMENTED**, **VERIFIED**, **NOT VERIFIED**, and **BLOCKED**. Never fabricate commands, output, test results, or production readiness.

## Structure

- `AGENTS.md` — master operating contract.
- `.agents/rules/` — modular engineering/security rules.
- `.agents/workflows/` — repeatable implementation and audit procedures.
- `.agents/checklists/` — focused gates.
- `.agents/templates/` — planning and evidence-report formats.
- `.agents/examples/` — concrete verification examples.
- `docs/` — installation, philosophy, architecture, and contribution guidance.

## Design principles

1. Server-side truth over client claims.
2. Real runtime verification over static confidence.
3. Negative tests are first-class requirements.
4. Root-cause repair over symptom patching.
5. Real integrations for real features; test doubles only where intentionally scoped.
6. Least privilege and fail-closed security boundaries.
7. Evidence before completion claims.

## Inspirations

The design is independently authored and informed by established patterns from AI-agent rule libraries, secure coding rule systems, Claude guardrails, OWASP ASVS, and Google Antigravity's current rules/workflows model. It does not copy source text from those projects.

See `docs/architecture.md` for the design rationale and `docs/antigravity.md` for platform mapping.

## License

MIT
