---
layout: docs
title: Account & billing
permalink: /account-billing/
---

Caia Coder is a **subscription product**. Every paid tier includes the **full product** (agent, editor, integrations, scheduler, marketplace). Plans differ by **monthly token pool** and billing model, not by feature paywalls.

## Plans overview

| Plan | Price (USD) | Monthly token pool | Notes |
| ---- | ----------- | ------------------ | ----- |
| **BYOM** | $10 / month | 0 included (BYOK) | You pay model providers directly; see [Models](models/) |
| **Basic** | $25 / month | 3M tokens | Unlimited BYOM profiles on top of included pool |
| **Pro** | $125 / month | 15M tokens | Unlimited BYOM profiles |
| **Pro+** | $250 / month | 30M tokens | Unlimited BYOM profiles |
| **Enterprise** | Contact sales | Custom | SSO, air-gapped deploy, custom integrations |

Billing cycles are typically **30-day** periods. **Annual** billing may be available with a lower effective monthly price; capabilities are the same.

Sign up and manage payment at [account.coder.caiaplatform.com](https://account.coder.caiaplatform.com).

## What counts toward your pool

- **Hosted / Caia-managed models** on Basic, Pro, and Pro+ consume your included monthly bucket.
- **BYOK runs** (your API keys) may appear in usage views but are tracked separately from the included bucket on normal plans.
- **BYOM subscribers** are not blocked by Caia’s included-token exhaustion gate; limits come from your provider account instead.

## In-app billing views

Open **Settings** in the workbench:

| View | Purpose |
| ---- | ------- |
| **Billing** | Plan, payment method, invoices, top-up |
| **Plan & usage** | Token usage, usage windows, pool remaining |
| **Usage / Spending** | Session-level estimates on this device |

Banners may appear when:

- Monthly token pool is exhausted
- A configured usage time window ended
- Account session is invalid (**Sign in again**)

When restricted, agent chat, scheduler, and marketplace-driven features may be disabled until billing or sign-in is resolved.

## Top-up and overage

You can buy **on-demand top-up** in USD when your operator enables it. Top-up credits extend your effective pool (plan tokens + top-up balance). Once the combined pool is fully consumed, premium actions are gated again.

Use **Billing** to see the approximate tokens for a top-up amount at the account server’s published rate.

## BYOM vs normal plans

| Topic | Normal plan | BYOM |
| ----- | ----------- | ---- |
| Included tokens | Yes (3M–30M by tier) | No Caia pool |
| Who bills model usage | Caia (included + top-up) | Your provider (OpenAI, Anthropic, Google, etc.) |
| Model selection | Caia hosted + BYOK profiles | BYOK profiles only |
| Product features | Full | Full |

Day-to-day BYOM: choose BYOM at signup → **Settings → Models** → add/select BYOK profile → pick it in the model dropdown before **Run** or **Send**.

## Students

Student discounts apply when verified with an approved **academic email**. Discounts apply to renewals while you remain verified; re-verify after changing your student email.

## Enterprise

Contact sales for:

- Custom token pool sizing
- Air-gapped deployments
- SSO
- CAIA Studios MCP agent linking
- Custom integrations

Email: support@caiaplatform.com (general) or your account representative.

## Legal & policies

Subscription and payment are governed by policies on the marketing site:

| Policy | URL |
| ------ | --- |
| Privacy | https://coder.caiaplatform.com/privacy |
| Terms of service | https://coder.caiaplatform.com/terms-of-service |
| Refund | https://coder.caiaplatform.com/refund-policy |
| Cancellation | https://coder.caiaplatform.com/cancellation |

## Billing support

- **Billing questions:** [billing@caiaplatform.com](mailto:billing@caiaplatform.com)
- **Payment portal:** **Settings → Billing → Manage billing** (when configured by your operator)
- **More FAQ:** [Troubleshooting & FAQ](troubleshooting/)
- **Support guide:** https://coder.caiaplatform.com/support
