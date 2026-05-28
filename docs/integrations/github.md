---
layout: page
title: GitHub
permalink: /integrations/github/
---

## Environment variables

| Variable | Description |
| -------- | ----------- |
| `CAIA_GITHUB_TOKEN` | Personal access token or fine-grained token |
| `CAIA_GITHUB_API_URL` | Optional **GitHub Enterprise** API base (e.g. `https://github.example.com/api/v3`) |

Tokens are **vault-bindable**; leave the UI field empty and bind `CAIA_GITHUB_TOKEN` in the [local vault](../local-vault/).

## Example scenarios

- **Open a PR** — Ask the agent to commit on a branch and open a pull request with a filled description (when `gh` is available and the token has repo scope).
- **Issue triage** — List or summarize open issues matching a label; draft a reply or a “needs-info” comment (you review before posting).
- **Release prep** — Ask for changelog text from merged PR titles or compare two tags via the API.
- **Org / Enterprise Server** — Set `CAIA_GITHUB_API_URL` for GitHub Enterprise and ask for the same workflows against your internal host.
- **Workflow hygiene** — Inspect `.github/workflows` in the workspace and ask for fixes to triggers, permissions, or action versions (no live repo change until you approve).
- **Search code** — Combine local repo search with questions about remote default branch protection or branch rules if the token allows.

The agent drives GitHub through **terminal commands** you request (`gh`, `git` with HTTPS remote, `curl` to the API). Match token **scopes** to the action (contents, issues, pull requests, etc.).

## Related

- Sidebar **Git** panel — local workspace Git, distinct from GitHub API automation.

[← All integrations](../integrations/)