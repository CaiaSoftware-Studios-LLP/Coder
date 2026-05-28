---
layout: docs
title: Marketplace
permalink: /marketplace/
---

The **Marketplace** sidebar is a **configuration surface**, not an extension marketplace like VS Code’s. It stores:

1. **URLs and non-secret defaults** in **browser storage** (per browser profile), and  
2. On **Save**, selected values are sent to the server and merged into **per-run environment** for agent tools (together with **Settings → Agent**).

Use **Settings → Agent → Integrations** for API tokens, keys, and long JSON (e.g. Google service account). The Marketplace copy in the UI reminds you that **creating** Confluence pages or Google Docs requires those integration fields, not only bookmarks here.

## What “Save” does

- Persists bookmark-style fields locally in the browser.
- Pushes integration-related env keys to the backend so each **Run agent** (and scheduled jobs that snapshot env) sees consistent values.
- **PostgreSQL**, **JFrog**, **GitHub**, and similar: passwords/tokens are often left empty in the UI and supplied via the [local vault](../local-vault/) instead.

## Sections (typical)

The HTML UI groups tiles such as:

- **Figma** — `CAIA_FIGMA_FILE_URL`, optional workspace-relative `CAIA_FIGMA_LIBRARY_PATH` for design-aligned code and assets.
- **Google Cloud** — `CAIA_GCP_PROJECT`, `GOOGLE_CLOUD_PROJECT`, `CAIA_GCP_REGION`, optional `CAIA_GCP_CONSOLE_URL` (credentials remain in Settings / ADC / keys).
- **Docker** — `DOCKER_HOST`, optional compose file path and `COMPOSE_PROJECT_NAME` so agent terminal steps use the same engine as the UI server. **Test Docker** runs `docker version` / `docker ps` on the server.
- **SAP** — landscape bookmarks (OData/Fiori base URL, host, port, SID, client, module focus) for FI, CO, MM, SD, etc.
- **Observability** — Prometheus, app `/metrics`, Grafana URLs (and API key often from vault) for metrics and dashboards during agent runs.
- **Kubernetes** — kubeconfig path, context, namespace (see [Kubernetes](../integrations/kubernetes/)).
- **JFrog**, **GitHub**, **PostgreSQL** — URLs and non-secrets; tokens/passwords via vault when fields are empty.

Exact field labels match the live **Marketplace** panel in the workbench.

## Live preview panel

The **Live preview** activity opens a **static** Node-based server (`tools/live-preview-server`) with reload. It is **not** a bundler:

- For **Vite/React dev**, run `npm run dev` in the **integrated terminal**; when the dev server prints a `localhost` URL, Caia can open it automatically.
- For static sites, use **Start live server** after `npm install` in `tools/live-preview-server`, and optional **Node executable** path if `node` is not on the server `PATH` (`CAIA_TERMINAL_PATH` / live preview path field).

## Relationship to Integrations

| Concern | Marketplace | Settings → Integrations |
| ------- | ----------- | ------------------------ |
| Design file URL, GCP region, Docker host | Yes | Optional duplicates |
| API tokens, service account JSON | Prefer vault or Integrations | Yes |
| Confluence / Google Docs **write** tools | Needs Integrations + optional vault | Yes |

See [Integrations](../integrations/) for each external system.

## Related

- [Local vault](../local-vault/)
- [Scheduler](../scheduler/) (snapshots Marketplace-derived env into `.caia/sre_schedules.json`)