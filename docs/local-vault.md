---
layout: page
title: Local vault
permalink: /local-vault/
---

The **local credential vault** stores named secrets **encrypted on disk** on the machine running the Caia agent server. The UI to manage it lives under **Settings** (Local credential vault section).

## Files and crypto

- **Directory:** `~/.caia/` (mode `700`).
- **Key file:** `vault.key` — Fernet symmetric key (chmod `600`).
- **Encrypted blob:** `vault.enc` — JSON payload encrypted with that key.
- **Lock file:** `vault.lock` — coordinates access across processes (file locking; thread lock fallback where `fcntl` is unavailable).

1. **Named entries** — arbitrary secret values (tokens, JSON blobs, passwords) stored under a name you choose (e.g. `grafana_prod`).
2. **Bindings** — map a **`CAIA_*` or standard env name** to an entry name. At run time, if the UI sends an **empty** value for that variable, the server **fills it from the vault** for that run. Non-empty UI values **override** the vault.

This lets you keep tokens out of browser fields and out of committed files.

## Bindable variables

The server only applies bindings for keys listed in `VAULT_BINDABLE_KEYS` in `caia_local_vault.py`, including:

The server only applies bindings for **supported** keys (the Settings UI lists every bindable variable). Typical groups include:
- **Confluence:** `CAIA_CONFLUENCE_BASE_URL`, `CAIA_CONFLUENCE_EMAIL`, `CAIA_CONFLUENCE_API_TOKEN`, `CAIA_CONFLUENCE_SPACE_KEY`
- **Google:** `CAIA_GOOGLE_SERVICE_ACCOUNT_JSON`, `CAIA_GOOGLE_OAUTH_ACCESS_TOKEN`
- **Observability:** `CAIA_PROMETHEUS_URL`, `CAIA_METRICS_URL`, `CAIA_GRAFANA_URL`, `CAIA_GRAFANA_API_KEY`
- **JFrog:** `CAIA_JFROG_URL`, `CAIA_JFROG_ACCESS_TOKEN`
- **GitHub:** `CAIA_GITHUB_TOKEN`, `CAIA_GITHUB_API_URL`
- **PostgreSQL:** `DATABASE_URL`, `CAIA_POSTGRES_*`, `PGHOST`, `PGPORT`, `PGUSER`, `PGPASSWORD`, `PGDATABASE`, `PGSSLMODE`
- **Kubernetes:** `CAIA_KUBECONFIG_PATH`, `CAIA_K8S_CONTEXT`, `CAIA_K8S_NAMESPACE`
- **SAP:** `CAIA_SAP_*` (OData URL, host, port, user, password, SID, client, modules focus)

If the encrypted file is corrupt or unreadable, merge falls back to incoming secrets only (no vault values).

## Operational notes

- **Backup:** treat `vault.key` + `vault.enc` like any key material; loss of `vault.key` means secrets are not recoverable.
- **Rotation:** add new entries, rebind, then remove old entries after confirming runs work.
- **CI / headless:** the vault is per user home directory; automation often uses plain env vars or a secret manager instead.

## Related

- [Marketplace](../marketplace/) — often leaves token fields empty so the vault supplies them.
- [Integrations](../integrations/) — documents each service’s required env vars.