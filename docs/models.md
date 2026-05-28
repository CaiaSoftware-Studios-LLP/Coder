---
layout: docs
title: Models
permalink: /models/
---

Caia Coder routes agent and chat requests through a **model profile** you select in the title bar. How billing and limits apply depends on your **plan** (see [Account & billing](account-billing/)).

## Model types

| Type | Who provides the API | Typical plan |
| ---- | -------------------- | ------------ |
| **Caia-hosted** | Caia infrastructure (e.g. cloud LLM endpoints) | Basic, Pro, Pro+ |
| **BYOK (bring your own key)** | You — keys stored in Settings or vault | Any plan; required on BYOM |
| **Local (operator-configured)** | Your deployment (e.g. Ollama on the server) | Self-hosted / enterprise |

## Choosing a model

1. Open the **Model** dropdown in the title bar.
2. Select a preset or a BYOK profile you created under **Settings → Models**.
3. Run the agent or send chat — usage is attributed per your plan rules.

If **Run** or **Send** is disabled on BYOM, ensure a **BYOK profile** is selected; BYOM does not use Caia’s default hosted model list without your keys.

## BYOK profiles

Under **Settings → Models**:

1. Add a profile with your provider API key and model ID.
2. Name the profile for easy recognition.
3. Select it in the title bar before each session.

Secrets can also flow from the [Local vault](local-vault/) when UI fields are empty and bindings match `CAIA_*` variables.

## Hosted models and token pools

On Basic, Pro, and Pro+:

- Hosted model usage counts toward your **monthly included pool**.
- Monitor remaining balance in **Settings → Plan & usage**.
- Use **top-up** or upgrade tier if you exhaust the pool (see [Account & billing](account-billing/)).

## BYOM (bring your own model)

On the BYOM commercial tier:

- Same product features as other tiers.
- Model calls use **your keys**; charges appear on your provider bill.
- Caia’s centrally hosted provider queue paths are not used.
- Your practical limits are provider quotas and account standing, not Caia’s included-token cap.

## Operator / self-hosted models

When your organization runs Caia Coder on its own infrastructure, operators may configure:

- **Ollama** or other local inference on the workspace server
- **Vertex AI** or enterprise gateways via environment variables
- Model allowlists and routing in server config (not in this public repo)

Ask your platform team for endpoint URLs, allowed model IDs, and compliance rules. Deployment patterns are summarized in [Deployment](deployment/).

## Safety and consent

Regardless of model, **Approve destructive actions** and scheduler **destructive** flags still apply to risky terminal, HTTP, Kubernetes, and database operations.

## Related

- [Account & billing](account-billing/) — plans, pools, BYOM
- [IDE features](ide-features/) — title bar controls
- [Local vault](local-vault/) — API keys as secrets
