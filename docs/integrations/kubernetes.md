---
layout: page
title: Kubernetes
permalink: /integrations/kubernetes/
---

When kubeconfig and context are available to the agent, it can perform **cluster checks** and other deploy-related Kubernetes operations you request.

## Example scenarios

- **Cluster health snapshot** — Ask for nodes, pods in a namespace, and whether the cluster answers `cluster-info`-style checks (read-only).
- **Debug a failing deployment** — Describe symptoms; ask the agent to inspect deployments, pods, events, and logs for a named workload (within allowed commands).
- **Pre-flight before apply** — Ask for a dry-run or manifest validation workflow if your process uses it; applying live manifests may require **destructive consent** in the UI.
- **Namespace inventory** — List namespaces, or summarize what runs in `staging` vs `production` contexts you have configured.
- **Image / rollout questions** — Ask which image tag a deployment uses or whether a rollout finished, based on cluster state.
- **Scheduled checks** — Use the [scheduler](../scheduler/) with a playbook markdown file to re-run read-only cluster checks on a cadence (destructive apply remains opt-in per job).

`kubectl` must be installed on the **server** that runs the agent, with a valid kubeconfig path.

## Environment variables

| Variable | Description |
| -------- | ----------- |
| `CAIA_KUBECONFIG_PATH` | Path to kubeconfig file on the **server** running the agent |
| `CAIA_K8S_CONTEXT` | Active context name |
| `CAIA_K8S_NAMESPACE` | Default namespace for operations |

These keys are **vault-bindable**—see [Local vault](../local-vault/).

Set context via the [Marketplace](../marketplace/) Kubernetes tile where exposed in the UI, then **Save**.

## Safety

**Mutating** cluster operations (for example applying manifests) may fall under **destructive consent** rules in the main agent UI. **Scheduler** jobs need explicit destructive enablement per job.

[← All integrations](../integrations/)