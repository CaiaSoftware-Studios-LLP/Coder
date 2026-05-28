---
layout: docs-home
title: Documentation
permalink: /
---

**Caia Coder** is a **subscription** browser coding agent: Monaco editor, workspace tools, and an autonomous agent that reads and edits project files, runs terminal commands, and uses configured integrations—all inside a single workspace.

This site is **company and user documentation** for subscribers. To use the product, sign in at [account.coder.caiaplatform.com](https://account.coder.caiaplatform.com). For community conversation, bugs, and release notes, visit the [GitHub community repository](https://github.com/CaiaSoftware-Studios-LLP/Coder) ([Discussions](https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions), [Issues](https://github.com/CaiaSoftware-Studios-LLP/Coder/issues), [Changelog](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/CHANGELOG.md)).

**New here?** Start with [Getting started](getting-started/) or pick your role on [Documentation by audience](audiences/).

## Documentation map

### Onboarding & account

| Document | What it covers |
| -------- | -------------- |
| [Getting started](getting-started/) | Sign-up, workspace, first agent run |
| [Documentation by audience](audiences/) | Quick links by role (developer, SRE, billing, enterprise) |
| [Account & billing](account-billing/) | Plans, token pools, BYOM, top-up, students |
| [Models](models/) | Hosted vs BYOK, BYOM, operator routing |
| [Troubleshooting & FAQ](troubleshooting/) | Common issues and billing questions |

### Product features

| Document | What it covers |
| -------- | -------------- |
| [IDE features](ide-features/) | Explorer, editor, search, Git, terminal, agent panel, INTENT.md |
| [Marketplace](marketplace/) | Browser-stored bookmarks and per-run environment |
| [Local vault](local-vault/) | Encrypted `~/.caia` credential store |
| [SRE scheduler](scheduler/) | Time-based runs of playbooks with saved env |
| [Integrations](integrations/) | Confluence, Google, observability, K8s, Docker, Figma, SAP, JFrog, GitHub, PostgreSQL |

### Operations

| Document | What it covers |
| -------- | -------------- |
| [Deployment](deployment/) | SaaS, desktop, Docker/K8s, air-gap, operator duties |

## Product, account & legal

| Resource | URL |
| -------- | --- |
| Marketing site | https://coder.caiaplatform.com |
| Account portal | https://account.coder.caiaplatform.com |
| Privacy policy | https://coder.caiaplatform.com/privacy |
| Terms of service | https://coder.caiaplatform.com/terms-of-service |
| Refund policy | https://coder.caiaplatform.com/refund-policy |
| Cancellation policy | https://coder.caiaplatform.com/cancellation |

## Community & releases

- [Welcome](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/WELCOME.md) — repository overview
- [Support](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SUPPORT.md) — email and GitHub channels
- [CHANGELOG](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/CHANGELOG.md) — release notes
- [GitHub Discussions](https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions) — questions and ideas
- [GitHub Issues](https://github.com/CaiaSoftware-Studios-LLP/Coder/issues) — bugs and features

## Publish on GitHub Pages

1. Push the `docs/` folder on `main` to [github.com/CaiaSoftware-Studios-LLP/Coder](https://github.com/CaiaSoftware-Studios-LLP/Coder).
2. **Settings → Pages → Build and deployment → GitHub Actions** (workflow: `.github/workflows/jekyll-gh-pages.yml`).
3. Confirm **`docs/_config.yml`**: `url` = `https://CaiaSoftware-Studios-LLP.github.io`, `baseurl` = `/Coder`.

**Live site:** https://CaiaSoftware-Studios-LLP.github.io/Coder/
