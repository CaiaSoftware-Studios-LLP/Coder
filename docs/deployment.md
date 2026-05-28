---
layout: docs
title: Deployment
permalink: /deployment/
---

This page is for **operators**, **platform engineers**, and **enterprise admins** who run or evaluate Caia Coder outside the default SaaS offering. Application packaging source is maintained privately; this document describes what subscribers and operators should expect.

## Deployment options

| Option | Best for | Notes |
| ------ | -------- | ----- |
| **SaaS (browser)** | Individuals and teams | Sign in at your assigned URL; workspace runs on Caia-managed servers |
| **Desktop app** | Developers wanting a native shell | Electron-style packaging when offered by your operator |
| **Docker / Kubernetes** | Teams and enterprises | Container images and Helm charts supplied by Caia or your vendor |
| **Air-gapped** | Regulated environments | Enterprise tier; no outbound model traffic without your gateways |

## Operator responsibilities

Operators typically configure:

- **Authentication** — email/password, SSO (enterprise), session lifetime
- **Workspace storage** — persistent volumes for user project folders
- **Server PATH and shell** — so integrated terminal has `node`, `kubectl`, `docker`, etc.
- **Model routing** — hosted endpoints, Ollama, Vertex, or internal gateways (see [Models](models/))
- **Billing integration** — account server, usage windows, top-up (SaaS)
- **Network policy** — which integration endpoints agents may call

Document server-side variables in your internal runbook; user-facing secret storage is covered in [Local vault](local-vault/) and [Marketplace](marketplace/).

## Terminal and tools

The integrated **terminal runs on the server**, not only in the browser. If commands fail with “not found”:

1. Install tools on the workspace image or host.
2. Extend `PATH` via operator environment or **Settings** / server config as documented for your build.

## Optional VS Code workbench

Some deployments expose a **full VS Code–compatible workbench** in the browser via a separate URL pointed at the same workspace folder. This is optional operator configuration, not the default Caia Coder UI. See [IDE features](ide-features/#what-you-can-do-typical-scenarios).

## SRE and automation

- [SRE scheduler](scheduler/) — time-based runs of `ACTION.md` or other playbooks
- [Integrations](integrations/) — Kubernetes, observability, databases, CI systems
- Destructive automation requires explicit per-job flags and user consent settings

## Security and compliance

- Report vulnerabilities per [Security policy](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SECURITY.md).
- Credentials: prefer [Local vault](local-vault/) over plain text in repos.
- Review agent **consent** settings for production workspaces.
- Enterprise: discuss data residency, SSO, and air-gap requirements with Caia sales.

## Getting a deployment package

- **Enterprise:** contact support@caiaplatform.com or your account team.
- **Self-hosted evaluation:** request through sales; include expected user count and integration list.

## Related

- [Getting started](getting-started/) — end-user onboarding
- [Models](models/) — BYOK and operator routing
- [Account & billing](account-billing/) — SaaS plans vs enterprise
