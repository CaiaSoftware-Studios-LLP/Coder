---
layout: docs
title: Getting started
permalink: /getting-started/
---

This guide is for **new subscribers** and **developers** opening Caia Coder for the first time.

## Who this is for

| You are… | Start here |
| -------- | ---------- |
| Individual developer | Steps 1–5 below, then [IDE features](ide-features/) |
| Team member | Same as above; ask your admin for workspace URL and SSO if used |
| SRE / platform engineer | [Scheduler](scheduler/), [Integrations](integrations/), [Deployment](deployment/) |
| Billing / account owner | [Account & billing](account-billing/) |
| Enterprise buyer (evaluating) | [Community repo](https://github.com/CaiaSoftware-Studios-LLP/Coder), [Security policy](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SECURITY.md), [Deployment](deployment/) |

## 1. Create an account

1. Visit the [Coder marketing site](https://coder.caiaplatform.com) or your organization’s sign-in URL.
2. Open **Sign up** or go to [account.coder.caiaplatform.com](https://account.coder.caiaplatform.com).
3. Complete email verification and choose a plan (see [Account & billing](account-billing/)).

**Student discounts:** use an approved academic email; re-verify if you change addresses.

## 2. Open your workspace

After sign-in, open the Caia Coder web UI (browser) or desktop app if your operator provides one.

1. **Pick a workspace folder** — the project root the agent may read and write (title bar → **Workspace** → **Pick**).
2. Confirm the path is correct before your first agent run.

## 3. Write INTENT.md

Create or edit **INTENT.md** in the workspace root. This file is injected on every autonomous run.

Minimum content:

- **Goal** — what “done” looks like in one paragraph.
- **Non-goals** — what not to change.
- **Acceptance criteria** — bullets you can check off.

See [Writing intent markdown](ide-features/#writing-intent-markdown-so-the-agent-succeeds) for full guidance.

## 4. Configure models (optional)

- **Hosted plans (Basic, Pro, Pro+):** choose a model from the title bar dropdown; usage counts toward your monthly token pool.
- **BYOM plan:** add a BYOK profile under **Settings → Models** and select it before **Run** (see [Models](models/) and [Account & billing](account-billing/)).

## 5. Run your first agent task

1. Load **INTENT.md** (title bar).
2. Type a focused instruction in the **Agent** panel (e.g. “List the main modules and suggest a test plan”).
3. Click **Run agent**.
4. Review diffs and terminal output before accepting destructive actions.

Enable **Pause after tool** and **Approve destructive actions** while learning the product.

## 6. Add integrations (when needed)

Use **Marketplace** for per-run environment fields and **Local vault** for secrets. See [Integrations](integrations/) for Confluence, GitHub, Kubernetes, Docker, databases, and more.

## 7. Get help

This repository is the **community hub** for subscribers (docs, changelog, Discussions, Issues)—not the product source code.

| Need | Where |
| ---- | ----- |
| Documentation | https://CaiaSoftware-Studios-LLP.github.io/Coder/ |
| Release notes | [CHANGELOG](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/CHANGELOG.md) |
| How-to questions | [GitHub Discussions](https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions) |
| Bugs | [GitHub Issues](https://github.com/CaiaSoftware-Studios-LLP/Coder/issues) |
| Billing | [account.coder.caiaplatform.com](https://account.coder.caiaplatform.com) or billing@caiaplatform.com |
| General support | support@caiaplatform.com |
| Security | security@caiaplatform.com — [Security policy](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SECURITY.md) |

## Next steps

- [IDE features](ide-features/) — explorer, Git, terminal, agent panel
- [Marketplace](marketplace/) — integration bookmarks and env per run
- [Local vault](local-vault/) — encrypted credentials
- [Troubleshooting & FAQ](troubleshooting/)
