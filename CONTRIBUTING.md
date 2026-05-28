# Contributing to Caia Coder

Thank you for helping improve Caia Coder’s **public community repository**.

## What this repository is

**Caia Coder** is a **subscription product**. Customers use the hosted application and [account portal](https://account.coder.caiaplatform.com).

**This GitHub repo** is the public home for:

| Purpose | How to participate |
| ------- | ------------------ |
| **Company & user documentation** | Pull requests that edit `docs/` |
| **Changelog** | Maintainers update [CHANGELOG.md](CHANGELOG.md) when shipping user-facing releases |
| **Community discussion** | [GitHub Discussions](https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions) — see [DISCUSSIONS.md](DISCUSSIONS.md) |
| **Product feedback** | [GitHub Issues](https://github.com/CaiaSoftware-Studios-LLP/Coder/issues) (bugs and features) |

**Not in this repo:** private application source, CI for the product app, or subscription billing. Do not expect PRs here to change deployed Caia Coder binaries directly—they improve public docs and help us triage feedback.

## What you can contribute

| Area | Examples |
| ---- | -------- |
| **User docs** (`docs/`) | Clarify IDE features, integrations, billing, troubleshooting |
| **Release notes** | Maintainers add entries to [CHANGELOG.md](CHANGELOG.md) when publishing a release |
| **Issues** | Bug reports and feature requests about the **subscription product** |
| **Discussions** | Q&A and ideas ([DISCUSSIONS.md](DISCUSSIONS.md)) |

## Ground rules

- Follow the [Code of Conduct](CODE_OF_CONDUCT.md).
- Search existing Issues and Discussions before opening duplicates.
- Do not post secrets, API keys, or customer data.
- Keep pull requests focused on one topic.
- For **billing, refunds, or account access**, use [billing@caiaplatform.com](mailto:billing@caiaplatform.com) or the [account portal](https://account.coder.caiaplatform.com)—not a public Issue.

## Documentation contributions

1. Fork the repository and create a branch.
2. Edit Markdown under `docs/` (Jekyll with the `minima` theme).
3. Preview locally:

   ```bash
   cd docs
   bundle install
   bundle exec jekyll serve
   ```

4. Open a pull request against `main` with a clear description of who benefits (e.g. “SRE users configuring scheduler destructive flags”).

Use the same tone as existing pages: practical tables, short sections, links between related docs.

**Canonical doc URLs:** https://CaiaSoftware-Studios-LLP.github.io/Coder/ (see [README.md](README.md)).

## Bug reports and features

- **Security:** do not use public Issues — see [SECURITY.md](SECURITY.md).
- **Bugs:** use the bug report template; include your **plan** (BYOM, Basic, Pro, etc.), **deployment** (SaaS vs self-hosted), and steps to reproduce.
- **Features:** use the feature request template; explain the user problem and expected behavior.

## Pull request process

1. Fill in the PR template.
2. For doc-only changes, confirm links resolve and headings match Jekyll `permalink` paths.
3. Maintainers will review and merge when ready.

## Questions?

- [GitHub Discussions](https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions)
- [support@caiaplatform.com](mailto:support@caiaplatform.com)
