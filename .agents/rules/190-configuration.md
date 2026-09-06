# Configuration and Secrets

**CRITICAL:** never hardcode secrets or commit credentials. Validate required configuration at startup and fail fast for mandatory missing values.

Separate development, test, staging, and production configuration. Do not make production behavior depend on a development-only bypass. Prefer managed secret storage in deployment and least-privilege credentials.

Review environment variable names and API base URLs for consistency across local, CI, and deployment environments. Never print secret values while debugging configuration.