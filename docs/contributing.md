# Contributing

Contributions should make agent behavior more operational, testable, and secure.

## Rule quality

Prefer concrete instructions over generic advice. A strong rule tells the agent what to inspect, what to do, what failure looks like, and what evidence is required.

## Changes

- Preserve framework neutrality in core rules.
- Add specialized guidance rather than weakening core controls.
- Avoid copying external repositories verbatim; summarize/adapt ideas independently.
- Add or update a workflow/checklist when introducing a new verification category.
- Keep examples realistic and security-conscious.

## Review standard

Ask whether an agent could still create disconnected endpoints, fake authentication, trust client authorization, use accidental production mocks, skip migrations, swallow errors, or claim success without runtime evidence. If yes, improve the rulebook.