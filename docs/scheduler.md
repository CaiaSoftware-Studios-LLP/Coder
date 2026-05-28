---
layout: docs
title: SRE scheduler
permalink: /scheduler/
---

The **SRE scheduler** runs **autonomous agent sessions** on a timer, using a markdown playbook in the workspace instead of ad-hoc chat.

## Concepts

- **Playbook file** — default **`ACTION.md`** in the workspace root; the UI can point a job at another `*.md` path.
- **Job** — includes schedule, enabled flag, optional **destructive tools** allowance, and last-run metadata.
- **Persistence** — jobs and a snapshot of integration-related env live in **`<workspace>/.caia/sre_schedules.json`**.
- **Registry** — workspaces with schedules are registered on the server so a background loop (~45s interval) can scan and run due jobs.

## Schedule types

Supported `schedule.type` values:

| Type | Behavior |
| ---- | -------- |
| `once` | Fires once at `run_at` (ISO datetime with timezone); then disables the job |
| `minutes` | Every `interval_minutes` (1–59) since last run |
| `hourly` | Once per local clock hour after the configured `time` minute |
| `daily` | Every day at configured local `time` |
| `weekly` | On allowed weekdays at `time` |
| `biweekly` | Alternating ISO weeks (parity stored on the job) |
| `monthly` | On `day_of_month` (clamped to valid calendar day) at `time` |

Each schedule carries a **timezone** name (IANA, e.g. `America/New_York`); invalid values fall back to **UTC**.

## Limits

- **Max jobs per workspace:** 48 (`MAX_JOBS`).
- **Max env keys** in the stored snapshot: 64 (`MAX_ENV_KEYS`).

## Destructive actions

Scheduled runs **do not** show the interactive consent card. Destructive tools are **off by default** for scheduler jobs; enable **only** on jobs where you accept automated **terminal commands**, Kubernetes changes, mutating HTTP calls, and similar. The UI warns about this distinction.

## Env snapshot

When you save from the scheduler UI, the server stores a copy of **Marketplace-derived env** plus relevant **Settings → Agent** numeric/env fields so scheduled runs match what you expect (including Grafana token if it was present in saved marketplace state).

Configure **Marketplace** first, then save scheduler settings.

## Account and billing

If the commercial pool is exhausted or the usage window ended, the UI may disable scheduler actions (see in-app banners). The tick loop also respects usage slot secrets when configured.

## Related

- [IDE features](../ide-features/) — scheduler entry in the activity bar.
- [Marketplace](../marketplace/) — source of many injected env vars.
- [Local vault](../local-vault/) — secrets for integrations used during scheduled runs.