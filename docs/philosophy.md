# Philosophy

The repository optimizes for confidence, not code volume.

The central distinction is between implementation and evidence. Agents are probabilistic systems; source code that appears plausible is not proof of runtime behavior. Therefore every meaningful claim should have a corresponding executable verification method.

The rulebook deliberately emphasizes negative tests because authentication, authorization, validation, error handling, and integration failures often remain invisible on happy paths.

It also treats security and production readiness as part of feature completion, not a postscript. A feature that works only when security controls are disabled is not a working feature.