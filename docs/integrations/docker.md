---
layout: docs
title: Docker
permalink: /integrations/docker/
---

Docker is used through **normal terminal commands** in the workspace. Marketplace sets environment so those commands hit the same Docker daemon (and optional Compose project) as the UI server expects.

## Example scenarios

- **Local stack up/down** — Ask the agent to bring a Compose stack up, show `ps`, and tail logs for a failing service.
- **Image build and run** — From a `Dockerfile` in the workspace, ask for `docker build` and a sensible `run` invocation with published ports.
- **Debug “works on my machine”** — Compare container env, entrypoint, and mounted volumes against your compose file.
- **Registry pull issues** — Diagnose auth or image name problems when pulling from a private registry (using env and docs you provide).
- **Cleanup** — Prune unused images or stop old containers when you explicitly ask (destructive commands may need approval).
- **Parity with CI** — Ask the agent to mirror a CI job’s Docker build args or target stage locally.

Use **Test Docker** in Marketplace to confirm the UI server sees the same daemon before relying on agent-driven commands.

## Environment variables

| Variable | Description |
| -------- | ----------- |
| `DOCKER_HOST` | `unix://`, `tcp://`, `ssh://`, or `npipe://` (invalid values are rejected) |
| `CAIA_DOCKER_COMPOSE_FILE` | Path to a compose file (when configured) |
| `COMPOSE_PROJECT_NAME` | Compose project name (when configured) |

Set these in the [Marketplace](../marketplace/) **Docker** section. **Test Docker** in the UI runs `docker version` and `docker ps` on the **server**, not inside the workspace.

## Usage patterns

- Inspect containers: `docker ps`, `docker logs …`
- Compose workflows: `docker compose -f … up`, `docker compose ps`
- Same variables apply to **shell steps** in autonomous runs

## Security

Shell access is still subject to workspace boundaries and **destructive consent** for risky commands.

[← All integrations](../integrations/)