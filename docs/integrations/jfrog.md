---
layout: page
title: JFrog
permalink: /integrations/jfrog/
---

JFrog **Artifactory / Platform** URLs and tokens let the agent reference your artifact and registry infrastructure in prompts and shell work.

## Example scenarios

- **Dependency resolution** — Ask the agent to configure Maven, Gradle, npm, or pip to resolve against your Artifactory virtual repository URL.
- **Publish artifacts** — After a build in the workspace, ask for steps or scripts to upload JARs, Docker images, or generic files using the JFrog CLI or REST (token from vault).
- **Promotion flow** — Document or script copy between repositories (e.g. `libs-release-local` → `libs-staging`) following your org’s naming rules.
- **403 / auth debugging** — Paste an error; ask the agent to verify repository paths, token scope, and `.npmrc` / `settings.xml` patterns.
- **Xray / policy context** — Ask for how build failures might relate to policy when you describe Xray outcomes (agent uses your words and repo config, not live Xray unless you expose it).
- **Cleanup or retention** — Ask for maintenance commands or policies appropriate to your platform edition (confirm with admins before running deletes).

Keep **tokens** in the [local vault](../local-vault/) and reference only the non-secret URL in Marketplace when possible.

## Environment variables

| Variable | Description |
| -------- | ----------- |
| `CAIA_JFROG_URL` | Platform or Artifactory base URL |
| `CAIA_JFROG_ACCESS_TOKEN` | Identity or access token (commonly supplied via [local vault](../local-vault/) with an empty Marketplace field) |

## Usage

Typical flows: resolving dependencies, publishing build artifacts, or debugging repository configuration using **terminal commands** (`jfrog`, `curl`, language-specific clients).

[← All integrations](../integrations/)