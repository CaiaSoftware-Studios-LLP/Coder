---
layout: docs
title: Integrations
permalink: /integrations/
---

Integrations supply **environment variables** (and sometimes vault bindings) so the agent can reach external systems: publish documentation to Confluence or Google Docs, query metrics, talk to Kubernetes and Docker, and more.

Configure secrets in **Settings → Agent → Integrations** or the [local vault](../local-vault/). Use the [Marketplace](../marketplace/) for URLs, project IDs, Docker host, and other per-run bookmarks.

Each linked page includes an **Example scenarios** section with concrete workflows you can ask the agent to perform.

| Integration | What you can do |
| ----------- | ---------------- |
| [Confluence](confluence/) | Create wiki pages in Confluence Cloud |
| [Google Docs & Google Cloud](google/) | Create Google Docs; set GCP/Vertex defaults (see [Models](../models/) and operator config) |
| [Prometheus & Grafana](observability/) | Run PromQL and Grafana-backed checks when endpoints are configured |
| [Kubernetes](kubernetes/) | Cluster checks and deploy-related operations with valid kubeconfig |
| [Docker](docker/) | Use the same Docker/Compose engine as the server via configured env |
| [Figma](figma/) | Design URL and library path as context (no automatic Figma API in core UI) |
| [SAP](sap/) | Landscape context for OData/Fiori workflows |
| [JFrog](jfrog/) | Artifactory URLs and tokens for dependency and artifact workflows |
| [GitHub](github/) | API automation with `CAIA_GITHUB_TOKEN` (CLI or scripts in the workspace) |
| [PostgreSQL](postgresql/) | Connect with standard `PG*` / `DATABASE_URL` variables for migrations and SQL workflows |

## Consent and safety

Mutating operations may require **Approve destructive actions** and a **consent card** in the main agent UI. **Scheduled** runs use separate destructive flags on each job—see [SRE scheduler](../scheduler/).

## Related

- [Marketplace](../marketplace/)
- [Local vault](../local-vault/)