# DevOps and Deployment

Build artifacts must be reproducible. CI should run formatting/linting where applicable, tests, dependency/security checks, secret scanning, and build verification.

Define database migration execution, health checks, graceful shutdown, environment configuration, rollback considerations, and backup/recovery requirements. Deployment validation must verify the deployed application, not only the build artifact.

Do not claim production readiness without evidence for the deployment path and required runtime dependencies.