# Research Notes

This rulebook was designed after reviewing established agent-rule and application-security systems.

## AI-Agent-Coding-Rules / Agent Code Standards

Useful pattern: a drop-in, modular instruction library covering engineering principles, security, testing, architecture, database, CI/CD, observability, and a Definition of Done. This project adopts the modular-library concept but makes runtime evidence, authentication/authorization negative testing, and backend integration verification explicit.

Source: https://github.com/Emmanuel-Bamidele/AI-Agent-Coding-Rules

## TikiTribe / claude-secure-coding-rules

Useful patterns: a core-rule layer plus language/framework-specific modules, severity/enforcement levels, rule templates, and structural/security testing of the rule library. This project adapts those concepts without adopting Claude-specific file semantics as a requirement.

Source: https://github.com/TikiTribe/claude-secure-coding-rules

## DwarvesF / claude-guardrails

Useful patterns: defense in depth, explicit deny/guardrail layers, prompt-injection awareness, tests, and a distinction between stronger and lighter enforcement. Its warning that pattern hooks are not the true security boundary reinforces this project's principle that rules must not substitute for actual runtime/security controls.

Source: https://github.com/dwarvesf/claude-guardrails

## OWASP ASVS

Used as a security-verification reference because ASVS is explicitly intended as a basis for testing technical security controls and provides secure-development requirements. The rulebook does not reproduce ASVS text; it operationalizes relevant verification concepts at a higher level.

Source: https://owasp.org/www-project-application-security-verification-standard/

## Google Antigravity

Current Antigravity documentation describes workspace rules in `.agents/rules`, supports Manual, Always On, Model Decision, and Glob activation, and documents workflows as repeatable agent procedures. This repository therefore uses `.agents/rules` as its primary integration layout and keeps specialized workflows separate from always-on contract rules.

Source: https://antigravity.google/docs/rules-workflows
