# 195 — Secrets, API Keys, and Integration Configuration

**Severity: CRITICAL**  
**Activation: Model Decision — whenever implementation requires OAuth, AI, payments, email, storage, databases, queues, webhooks, third-party APIs, or any credential/configuration value.**

## Purpose

The agent must never leave the developer guessing where a required key, secret, endpoint, client ID, certificate, or other configuration value belongs. For every required configuration value, identify the **exact repository-relative path, variable name, configuration mechanism, and environment** before declaring the integration ready.

## Required behavior

When an integration requires configuration, the agent MUST:

1. Inspect the repository's existing configuration conventions before creating a new one.
2. Determine whether configuration is loaded from `.env`, `.env.local`, `.env.development`, `.env.test`, `.env.production`, a config module, deployment manifests, secret managers, CI/CD secrets, or another existing mechanism.
3. Reuse the established mechanism unless there is a documented reason not to.
4. Tell the developer exactly where each value must be supplied.
5. Distinguish **server-only secrets** from browser/client-exposed configuration.
6. Never print, commit, hardcode, or expose secret values.
7. Add or update a safe `.env.example` / configuration example when the repository convention supports it, containing variable names and placeholders only.
8. Document which values are required for local development, tests, CI, staging, and production.
9. If the required secret cannot be configured or accessed, mark the integration **BLOCKED** or **NOT VERIFIED** rather than pretending it works.

## Exact configuration handoff

For every required value, report a table with at least:

| Integration | Value | Exact path/location | Variable/config key | Environment | Client/server | Required? |
|---|---|---|---|---|---|---|

Example:

| Integration | Value | Exact path/location | Variable/config key | Environment | Client/server | Required? |
|---|---|---|---|---|---|---|
| Google OAuth | Client ID | `backend/.env.local` | `GOOGLE_CLIENT_ID` | local | server | yes |
| Google OAuth | Client secret | `backend/.env.local` | `GOOGLE_CLIENT_SECRET` | local | server | yes |
| AI provider | API key | `backend/.env.local` | `AI_API_KEY` | local | server | yes |

**The paths above are examples only. The agent MUST inspect the actual repository and replace them with the real paths. Never invent a path.**

## Integration-specific checks

### OAuth

Identify all required values, which OAuth provider owns them, the configured redirect/callback URL, allowed origins if applicable, scopes, and where each credential is configured. Verify that secrets remain server-side when the architecture requires it.

### AI / external API

Identify provider, API key/credential variable, base URL if configurable, model/deployment identifier if required, timeout/retry settings, and whether the request is server-side. Never put a private provider key into frontend source or a browser-exposed environment variable.

### Database / cache / queue

Identify connection URL or individual connection variables, TLS requirements, database name, and environment-specific configuration. Never expose credentials to the frontend.

### Email / storage / payments

Identify all credential variables and required IDs, endpoints, buckets, sender configuration, webhook secrets, and environment-specific values. Explicitly identify which values belong in CI/CD or a production secret manager instead of a committed file.

## Local setup instructions

When implementation requires developer action, the final report MUST include a concise **Configuration Required** section:

- exact file/path to create or edit
- exact variable names
- safe placeholder/example values where appropriate
- where to obtain each value (provider dashboard/documentation, without requesting the user paste the secret into chat)
- whether the value is needed for local/test/staging/production
- restart/reload command if configuration is read only at startup
- verification command or test that confirms configuration is loaded without printing the secret

If a configuration file is gitignored, state that explicitly. If a secret manager or CI secret is required, state the exact secret/config key expected by the application and the deployment environment where it must be created.

## Never do this

- Never say only: `Add your API key to the env file.`
- Never say only: `Configure OAuth.`
- Never invent `backend/.env` when the repository actually uses another path.
- Never ask the developer to paste a secret into source code or chat.
- Never commit real secrets.
- Never expose server secrets through frontend bundles.
- Never claim an integration is verified when required credentials were unavailable.

## Completion criterion

An integration is configuration-complete only when:

- every required value has an identified source;
- every value has an exact repository/deployment location and variable/config key;
- secret exposure boundaries are correct;
- safe example configuration is documented where appropriate;
- the application validates missing configuration clearly;
- available credentials were used to exercise the real integration, or the result is explicitly marked **NOT VERIFIED/BLOCKED**.
