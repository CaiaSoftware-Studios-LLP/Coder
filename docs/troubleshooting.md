---
layout: page
title: Troubleshooting & FAQ
permalink: /troubleshooting/
---

## Quick fixes

| Symptom | Try this |
| ------- | -------- |
| **Run** / **Send** disabled | Sign in again; check billing banners; on BYOM, select a BYOK model profile |
| Agent stops immediately | Check token pool and usage window in **Settings → Plan & usage** |
| Terminal: command not found | Ask operator to install tool or extend server `PATH` |
| Integration fails | Verify [Marketplace](marketplace/) fields and [Local vault](local-vault/) bindings |
| “Outside workspace” errors | Pick the correct **Workspace** folder; agent cannot read parent paths |
| Stale or wrong behavior | Update **INTENT.md**; add files via explorer **＋ context** |
| Scheduled job did nothing | Open [Scheduler](scheduler/); confirm playbook path and env snapshot |

## Billing & usage FAQ

### What features are included in each plan?

Every plan includes the full product: agent runs, editor, integrations, models, scheduler, and marketplace. Plans differ by **monthly token pool**, not feature access.

### How is usage measured?

Usage is tracked as **token estimates** from session history. Calendar-month usage appears in **Usage**, **Spending**, and **Billing** views for attribution on your device and account sync.

### Monthly vs annual billing?

Same product capabilities. Annual billing lowers effective monthly price with the same token attribution logic.

### Where are invoices and payment methods?

**Settings → Billing → Manage billing** when your operator configured a billing portal. Invoices load from the account server when signed in.

### Can I buy extra tokens?

Yes, when **on-demand top-up** is enabled. Enter an amount in **Billing** to see approximate tokens at the published USD-per-million rate.

### Can I continue after my plan pool is exhausted?

Yes, if **top-up balance** remains. Effective usage compares against plan tokens plus top-up. When both are consumed, the gate blocks premium actions again.

### BYOM vs normal plan?

**Normal plans:** Caia tracks a monthly included bucket for hosted models; BYOK usage is shown separately. **BYOM:** you pay providers directly; select BYOK profiles in **Settings → Models**; Caia hosted queue paths are off.

### Student discounts on renewal?

Yes, while verified on the same approved academic email. Re-verify after changing student email.

## Agent & workspace FAQ

### Does the agent remember previous sessions?

Continuity comes from **INTENT.md**, optional **`CAIA_MEMORY.md`**, workspace files, and browser-stored context for that workspace — not a separate global memory service. See [IDE features — Agent, context, and memory](ide-features/#agent-context-and-memory).

### Can the agent access the internet?

Mutating or broad HTTP is gated. Observability and integration URLs are limited to what you configure for the run.

### Are destructive commands allowed?

When **Approve destructive actions** is on, risky terminal, HTTP, Kubernetes, and database operations show a **consent card** before running. Scheduler jobs have separate per-job destructive flags.

## Community & support

| Channel | Use for |
| ------- | ------- |
| [GitHub Discussions](https://github.com/CaiaSoftware-Studios-LLP/Coder/discussions) | How-to, workflows, Q&A |
| [GitHub Issues](https://github.com/CaiaSoftware-Studios-LLP/Coder/issues) | Bugs and feature requests |
| support@caiaplatform.com | Account and product help |
| billing@caiaplatform.com | Invoices, plans, refunds |
| security@caiaplatform.com | Vulnerabilities ([policy](https://github.com/CaiaSoftware-Studios-LLP/Coder/blob/main/SECURITY.md)) |

See also [DISCUSSIONS.md](../DISCUSSIONS.md) for what belongs in Discussions vs Issues.

## Related docs

- [Getting started](getting-started/)
- [Account & billing](account-billing/)
- [Models](models/)
- [IDE features](ide-features/)
