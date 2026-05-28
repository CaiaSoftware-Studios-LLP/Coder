---
layout: docs
title: IDE features
permalink: /ide-features/
---

The Caia Coder UI is a **web workbench** (also available as a **desktop app**). It is not a full Visual Studio Code installation by default, but it mirrors familiar IDE ideas: files, search, Git, terminal, and an **Agent** panel that runs against your **Workspace** folder.

## Activity bar and sidebar

| Panel | Purpose |
| ----- | ------- |
| **Explorer** | File tree for the selected **Workspace**; refresh, collapse, new file/folder; multi-select (⌘/Ctrl-click); **＋ context** adds selected paths to what the agent can focus on |
| **Search** | Workspace search with optional case sensitivity, regex, include/exclude globs |
| **Live preview** | Static HTTP server with reload for built assets; see [Marketplace & live preview](../marketplace/#live-preview-panel) |
| **Git** | Git status and common operations for the workspace |
| **Marketplace** | Integration bookmarks and environment fields; see [Marketplace](../marketplace/) |
| **SRE scheduler** | Time-based agent runs driven by markdown in the repo; see [Scheduler](../scheduler/) |
| **Agent** | Chat, run log, and consent prompts for risky actions |
| **Terminal** | Integrated terminal on the **server** (not only in your browser); if `node` or other tools are missing, the operator can extend the server `PATH` or shell via documented environment variables in **Settings** / server config |
| **Settings** | Model defaults, integrations, billing, and **local vault** |

## Title bar

- **Workspace** — Path to the project folder the agent may read and write; **Pick** opens a folder chooser where the product supports it.
- **Model** — Which language model to use; presets may reflect environment defaults.
- **Pause after tool** — Stop after each agent step so you can steer before the next action.
- **Approve destructive actions** — When on, risky **terminal commands**, **mutating HTTP** calls, **Kubernetes apply**-style changes, and **database migration / DML**-style work can show a **consent card** before running (with a timeout you can configure in **Settings**).
- **Run agent** / **Stop** — Start a run, or stop after the current model step finishes (mid-stream cancel is not guaranteed).
- **Load INTENT.md** / **Save** — Load or save the **project intent** file (default name **INTENT.md**) that is injected as high-priority context for autonomous runs.

## Editor

- Syntax highlighting and editing for common languages.
- Tabs and unsaved (“dirty”) state behave like a typical code editor.

---

## Agent, context, and memory

Where this appears today:

| Topic | Where it is covered in this doc |
| ----- | ------------------------------ |
| **Agent panel** (chat, run log, consent) | [Activity bar and sidebar](#activity-bar-and-sidebar) — row **Agent** |
| **Starting / stopping runs** | [Title bar](#title-bar) — **Run agent** / **Stop** |
| **Steering each step** | [Title bar](#title-bar) — **Pause after tool** |
| **Project goals in every run** | [Title bar](#title-bar) — **INTENT.md**; detailed guidance in [Writing intent markdown](#writing-intent-markdown-so-the-agent-succeeds) |
| **Account limits affecting the agent** | [Account and limits (UI)](#account-and-limits-ui) |

**Context** the agent can use (together, not instead of clear instructions):

- **INTENT.md** (or the intent file you load) — main product spec for the workspace; always keep it aligned with reality.
- **Chat instructions** — What you type for this run (and your session’s instruction history, stored in the browser for that workspace).
- **Explorer “＋ context”** — Selected files and folders you add so the agent prioritizes them.
- **Optional `CAIA_MEMORY.md`** — If you create this file in the workspace, a short excerpt can be included each run so decisions and “already done” notes are not forgotten across runs. Keep it brief and factual.

**“Memory” in practice:** there is no separate global memory database in the docs product. Continuity comes from **files in the workspace** (INTENT, optional memory file, code, comments), **browser-stored project context** for that workspace, and what you paste into chat. Very large repos rely on the agent **narrowing** to relevant areas (index-assisted discovery plus targeted reads), not loading every file every time.

---

## Writing intent markdown so the agent succeeds

The product injects your **INTENT.md** (or the path you load) as core context. A clear file reduces ambiguity and failed runs.

### What to put at the top

- **Goal** — One short paragraph: what “done” looks like (e.g. “Add CSV export to the billing page”).
- **Non-goals** — What to avoid (e.g. “Do not change the auth module”).
- **Constraints** — Language/runtime, frameworks, style, performance, or compatibility (e.g. “Python 3.11 only”, “must work offline”).
- **Acceptance criteria** — Bullet list you could check off (e.g. “`pytest` passes”, “UI shows error on invalid input”).


### Structure the middle

- **Context** — Links or paths to the most relevant folders/files (“start from `src/api/`”).
- **Steps (optional)** — Numbered phases if the task is large (“1) schema 2) API 3) UI”).
- **Examples** — Sample input/output, API payloads, or screenshots described in text.

### Style tips

- Prefer **short sections and bullets** over one huge paragraph.
- Use **explicit file paths** when you care which files are touched.
- If integrations matter, say so in plain language (“publish summary to our wiki after”) and ensure [Integrations](../integrations/) and [Marketplace](../marketplace/) are configured.
- **Refresh intent** as the project evolves; stale INTENT misleads the agent.

### Scheduler playbooks

For [scheduled runs](../scheduler/), use a dedicated markdown playbook (often **ACTION.md**) with the same discipline: clear objective, frequency implied by the scheduler UI, and explicit checks (metrics, `kubectl` read-only, log lines). Destructive automation is opt-in per job.

---

## What you can do (typical scenarios)

- **Implement or refactor features** in the workspace using natural language plus INTENT.
- **Fix build/test failures** when logs or errors are in the repo or pasted into chat.
- **Explore the codebase** via explorer + search + agent context.
- **Run commands** in the integrated terminal (subject to consent for destructive operations).
- **Use configured integrations** — docs publishing, metrics, Kubernetes, Docker, databases, etc., when env and vault are set; see [Integrations](../integrations/).
- **Iterate with pause-after-tool** for sensitive or large changes.
- **Open optional full VS Code** in the browser when your operator configures a URL to a separate Code-compatible workbench pointing at the same folder.

## What the agent usually cannot or should not do

- **Guarantee correctness** — Always review diffs, tests, and security; models make mistakes.
- **Access arbitrary networks** — Mutating or broad HTTP is gated; observability URLs are limited to what you saved for the run.
- **Escape the workspace** — Paths that climb outside the chosen folder are rejected.
- **Bypass consent** — Destructive classes of actions require approval when that option is enabled (scheduled jobs use separate per-job rules).
- **See your screen or private apps** — Only workspace files, terminal on the server, and tools you configured.
- **Replace production change management** — Treat merges, deploys, and data changes as your responsibility.
- **Run forever** — Step limits and timeouts apply; very large tasks may need splitting.

---

## Account and limits (UI)

Banners may appear when:

- Monthly token pool is exhausted (**Settings → Billing**).
- A configured usage time window ended (**Settings → Plan & usage**).
- Account session is invalid (**Sign in again**).

When restricted, agent chat, scheduler, and marketplace-driven features may be disabled until the account or plan state is resolved.

See [Account & billing](../account-billing/) for plans, BYOM, top-up, and student discounts.

## Related

- [Marketplace](../marketplace/) — environment injected per run from saved fields.
- [Local vault](../local-vault/) — secrets when UI fields are empty.
- [Integrations](../integrations/) — external systems when configured.
- [Scheduler](../scheduler/) — recurring playbook runs.