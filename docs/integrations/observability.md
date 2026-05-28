---
layout: page
title: Prometheus & Grafana
permalink: /integrations/observability/
---

When Prometheus and Grafana URLs (and Grafana auth when needed) are present in the environment, the agent can **run metric queries** (for example PromQL) and use Grafana as configured.

## Example scenarios

- **“Why is staging red?”** — Ask the agent to query Prometheus for error rates, latency, or `up` for key jobs, using the saved Prometheus URL only.
- **Capacity check** — Request CPU/memory saturation or request-rate panels expressed as PromQL summaries for a namespace or service name you specify.
- **Compare before/after deploy** — After a deploy, ask for metric snapshots (e.g. 5m rate of 5xx) to compare verbally against an earlier state you describe.
- **Grafana dashboard discovery** — With Grafana URL and API key set, ask the agent to search or summarize relevant dashboards or panels for a keyword (e.g. “payments”, “kafka”).
- **App `/metrics` sanity** — If `CAIA_METRICS_URL` points at your app’s scrape endpoint, ask whether expected counters exist or look healthy (as text/scrape-style checks, not arbitrary URLs).
- **SRE playbook in `ACTION.md`** — Combined with the [scheduler](../scheduler/), recurring jobs can re-check the same saved endpoints for drift or failures.

Queries are limited to **configured** endpoints for the run (the agent cannot point at random URLs).

## Typical variables

| Variable | Role |
| -------- | ---- |
| `CAIA_PROMETHEUS_URL` | Prometheus base URL |
| `CAIA_METRICS_URL` | Optional app `/metrics` endpoint (context or checks) |
| `CAIA_GRAFANA_URL` | Grafana base URL |
| `CAIA_GRAFANA_API_KEY` | Grafana API token or service account token (often from [vault](../local-vault/)) |

Configure the **Observability** section in the [Marketplace](../marketplace/) and click **Save** so per-run env includes these keys.

## Behavior

Supported operations follow what the UI and server expose (for example PromQL against your saved Prometheus URL). The Marketplace UI notes that **saved** endpoints are passed to the agent for **this run**—not arbitrary URLs chosen by the model.

## Related

- [Kubernetes](../kubernetes/) — often paired for cluster metrics debugging.

[← All integrations](../integrations/)