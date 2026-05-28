# Caia Coder

Welcome to the official **community repository** for **Caia Coder**.

**Caia Coder** is a **subscription product** (browser coding agent and workspace UI). You subscribe, sign in, and use the app at [account.coder.caiaplatform.com](https://account.coder.caiaplatform.com) — you do not build or run the product from this GitHub repo.

## What this repository is for

| Use this repo to… | Where |
| ----------------- | ----- |
| **Read company & user documentation** | [`docs/`](docs/) and [documentation site](https://CaiaSoftware-Studios-LLP.github.io/Coder/) |
| **See what changed in the product** | [CHANGELOG.md](CHANGELOG.md) |
| **Ask questions and share ideas** | [GitHub Discussions](https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions) — see [DISCUSSIONS.md](DISCUSSIONS.md) |
| **Report bugs or request features** | [GitHub Issues](https://github.com/CaiaSoftware-Studios-LLP/Coder/issues) |
| **Find support & policies** | [SUPPORT.md](SUPPORT.md), [SECURITY.md](SECURITY.md), [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) |

**Not in this repo:** application source code, local builds of Caia Coder, or subscription billing (use the [account portal](https://account.coder.caiaplatform.com)). Legal terms live on the [marketing site](https://coder.caiaplatform.com).

## Canonical links

Use these URLs everywhere (README, Discussions, email, and the marketing site). They work from GitHub, GitHub Pages, and external sites.

| What | Canonical URL |
| ---- | --------------- |
| **Product documentation** (this repo, GitHub Pages) | https://CaiaSoftware-Studios-LLP.github.io/Coder/ |
| **GitHub repository** | https://github.com/CaiaSoftware-Studios-LLP/Coder |
| **Marketing site** | https://coder.caiaplatform.com |
| **Account & billing portal** | https://account.coder.caiaplatform.com |
| **Privacy policy** | https://coder.caiaplatform.com/privacy |
| **Terms of service** | https://coder.caiaplatform.com/terms-of-service |
| **Refund policy** | https://coder.caiaplatform.com/refund-policy |
| **Cancellation policy** | https://coder.caiaplatform.com/cancellation |
| **Support policy** (web) | https://coder.caiaplatform.com/support |

Legal text is maintained in the product website repository and published at **coder.caiaplatform.com** (not duplicated in this community repo).

## Start here

| Audience | Documentation |
| -------- | --------------- |
| **New subscribers** | [Getting started](https://CaiaSoftware-Studios-LLP.github.io/Coder/getting-started/) |
| **Developers** | [IDE features](https://CaiaSoftware-Studios-LLP.github.io/Coder/ide-features/), [Integrations](https://CaiaSoftware-Studios-LLP.github.io/Coder/integrations/) |
| **SRE / platform** | [Scheduler](https://CaiaSoftware-Studios-LLP.github.io/Coder/scheduler/), [Deployment](https://CaiaSoftware-Studios-LLP.github.io/Coder/deployment/) |
| **Billing / account owners** | [Account & billing](https://CaiaSoftware-Studios-LLP.github.io/Coder/account-billing/) |
| **Enterprise evaluators** | [Deployment](https://CaiaSoftware-Studios-LLP.github.io/Coder/deployment/), [Security policy](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SECURITY.md) |
| **All roles** | [Documentation by audience](https://CaiaSoftware-Studios-LLP.github.io/Coder/audiences/) |

**Browse on GitHub:** same guides live under [`docs/`](docs/) as Markdown (for editing and PRs). **Read online:** use the [documentation site](https://CaiaSoftware-Studios-LLP.github.io/Coder/) above.

## Repository contents

| Path | Purpose |
| ---- | ------- |
| [`docs/`](docs/) | Jekyll user documentation (published to GitHub Pages) |
| [WELCOME.md](WELCOME.md) | Welcome page for the community |
| [CHANGELOG.md](CHANGELOG.md) | Public release notes |
| [SUPPORT.md](SUPPORT.md) | Support channels (also on the [marketing site](https://coder.caiaplatform.com/support)) |
| [DISCUSSIONS.md](DISCUSSIONS.md) | When to use Discussions vs Issues |
| [SECURITY.md](SECURITY.md) | Vulnerability reporting |
| [CONTRIBUTING.md](CONTRIBUTING.md) | How to contribute docs and issues |
| [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) | Community standards |
| `.github/` | Issue templates, PR template, Pages workflow |

## Quick start (documentation site)

### Prerequisites

- Ruby 3.x
- Bundler

### Run locally

```bash
cd docs
bundle install
bundle exec jekyll serve
```

Open http://127.0.0.1:4000/Coder/ (matches `baseurl` in [`docs/_config.yml`](docs/_config.yml)).

## Publishing on GitHub Pages

1. Push to `main` on **github.com/CaiaSoftware-Studios-LLP/Coder** with the `docs/` folder committed.
2. In the repo: **Settings → Pages → Build and deployment → GitHub Actions** (workflow: [`.github/workflows/jekyll-gh-pages.yml`](.github/workflows/jekyll-gh-pages.yml)).
3. Confirm [`docs/_config.yml`](docs/_config.yml): `url` is `https://CaiaSoftware-Studios-LLP.github.io` and `baseurl` is `/Coder`.
4. Live site: **https://CaiaSoftware-Studios-LLP.github.io/Coder/**

If you rename the GitHub org or repository, update `_config.yml`, re-run the Pages workflow, and replace the URLs in this README and [WELCOME.md](WELCOME.md).

## Community & support

| Channel | Link |
| ------- | ---- |
| General | [support@caiaplatform.com](mailto:support@caiaplatform.com) |
| Billing | [billing@caiaplatform.com](mailto:billing@caiaplatform.com) |
| Security | [security@caiaplatform.com](mailto:security@caiaplatform.com) — [Security policy](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SECURITY.md) |
| Welcome | [WELCOME.md](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/WELCOME.md) |
| Support guide | [SUPPORT.md](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SUPPORT.md) |
| Discussions guide | [DISCUSSIONS.md](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/DISCUSSIONS.md) |
| Contributing | [CONTRIBUTING.md](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/CONTRIBUTING.md) |
| Code of Conduct | [CODE_OF_CONDUCT.md](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/CODE_OF_CONDUCT.md) |
| GitHub Discussions | https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions |
| GitHub Issues | https://github.com/CaiaSoftware-Studios-LLP/Coder/issues |
| Account portal | https://account.coder.caiaplatform.com |

## Commercial readiness

This repository includes what enterprise reviewers typically expect: license, contribution process, code of conduct, security policy, support policy, issue templates, and user documentation. **Legal policies** (privacy, terms, refund, cancellation) are published on the [marketing site](https://coder.caiaplatform.com) and linked above.

## License

MIT License — see [LICENSE](LICENSE).
