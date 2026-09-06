# Code Quality and Dependency Discipline

Prefer existing project conventions and dependencies over new abstractions or packages. Every dependency must have a clear need, maintenance/security rationale, and compatible license.

Keep changes small and reviewable. Remove dead code introduced by the change. Do not perform unrelated rewrites. Preserve public behavior unless the requirement explicitly changes it.

Quality checks are evidence, not decoration: run the project's formatter/linter/type checker/build where applicable and report actual results.