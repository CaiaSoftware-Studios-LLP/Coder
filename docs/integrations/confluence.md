---
layout: docs
title: Confluence
permalink: /integrations/confluence/
---

With credentials configured, you can ask the agent to **create Confluence Cloud pages** (for example runbook or API documentation) from your workspace.

## Example scenarios

- **Publish release notes** — Point the agent at `CHANGELOG.md` or release bullets in the repo and ask it to create a new Confluence page in your chosen space with that content.
- **API / onboarding docs** — After implementing an API, ask for a wiki page that describes endpoints, auth, and examples, sourced from your OpenAPI spec or README.
- **Runbooks and incident playbooks** — Turn a draft in the workspace into a titled runbook page (steps, contacts, rollback) for the operations space.
- **Design / architecture summaries** — Ask for a page that summarizes `ARCHITECTURE.md` or ADR files for stakeholders who live in Confluence.
- **Meeting or decision log** — Paste or reference notes in the workspace and ask for a dated Confluence page under a team space.

In each case, name the **space** (or rely on your default space key) and the **page title** you want. The body is stored as plain text inside Confluence (preserved layout in a single preformatted block).

## Required environment variables

| Variable | Description |
| -------- | ----------- |
| `CAIA_CONFLUENCE_BASE_URL` | Site wiki base, e.g. `https://your-org.atlassian.net/wiki` |
| `CAIA_CONFLUENCE_EMAIL` | Atlassian account email |
| `CAIA_CONFLUENCE_API_TOKEN` | API token (not your password) |
| `CAIA_CONFLUENCE_SPACE_KEY` | Default space key (optional if you always specify the space in instructions) |

Set these in **Settings → Agent → Integrations** or bind them in the [local vault](../local-vault/).

## Content format

Body text is sent to Confluence as **storage** HTML inside a single `<pre>` block so plain text and newlines are preserved.

- **HTTP 401/403** — wrong email/token or missing Confluence product on the site.
- **Unknown space** — fix `space_key` or set default in Integrations.
- **Empty body** — the tool rejects empty content; ensure the model passes `body`.

[← All integrations](../integrations/)