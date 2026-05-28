---
layout: page
title: Google Docs & Google Cloud
permalink: /integrations/google/
---

## Google Docs

Creates Google Docs via the **Docs API** using either:

| Mode | Variable |
| ---- | -------- |
| **Service account (recommended)** | `CAIA_GOOGLE_SERVICE_ACCOUNT_JSON` — full JSON as a single string (or pretty-printed) |
| **OAuth bearer fallback** | `CAIA_GOOGLE_OAUTH_ACCESS_TOKEN` |

The service account must be **granted access** to Drive/Docs (domain-wide delegation or share a folder with the service account email), depending on your Google Workspace policies.

Ask the agent in natural language to create a doc with a given title and body once credentials are set.

## Example scenarios (Google Docs)

- **Shareable spec** — Ask for a Google Doc titled like “Feature X — Technical spec” with sections pulled from your markdown files in the workspace.
- **Customer-facing summary** — Turn internal technical notes into a shorter doc for non-engineers (still verify tone and accuracy before sharing externally).
- **Test plan or checklist** — Generate a doc version of a QA checklist the team can comment on in Drive.
- **Meeting notes** — From bullets in the workspace, produce a dated Doc with action items.
- **Draft handoff** — Create a blank-titled doc with structured body text you can refine in the Google Docs UI (sharing and folder placement depend on your Drive / service-account setup).

Ensure the **service account** (or OAuth identity) can create files in the right Drive location for your organization.

## Google Cloud defaults (Marketplace / env)

For **Vertex**, **gcloud**, and documentation alignment, the Marketplace can inject:

- `CAIA_GCP_PROJECT` and `GOOGLE_CLOUD_PROJECT`
- `CAIA_GCP_REGION`
- Optional `CAIA_GCP_CONSOLE_URL`

**Credentials** for Vertex use **Application Default Credentials**: locally `gcloud auth application-default login`, on GCP an attached service account, or `GOOGLE_APPLICATION_CREDENTIALS`. API keys for Gemini/Vertex variants may live in **Settings** or the vault (`CAIA_GEMINI_API_KEY`, `CAIA_VERTEX_API_KEY`).

Full Vertex setup is described in the repository **agent README** (*Vertex API (Google Cloud) as model backend*).

## Example scenarios (Google Cloud / Vertex)

- **Model backend** — Use Vertex (or Gemini) as the chat model for the agent instead of a local Ollama instance, with project and region set in Marketplace and credentials on the server.
- **Consistent `gcloud` context** — With project and region injected per run, ask the agent to propose or run `gcloud` commands that match your org’s project (still subject to your IAM and consent settings).
- **Console deep links** — If you saved a console bookmark URL, ask the agent to reference it when explaining where to change quotas, IAM, or logs.

## Related

- [Local vault](../local-vault/) — optional binding for service account JSON or tokens.
- [Marketplace](../marketplace/) — project/region bookmarks.

[← All integrations](../integrations/)