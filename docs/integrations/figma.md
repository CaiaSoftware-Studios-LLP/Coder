---
layout: page
title: Figma
permalink: /integrations/figma/
---

Figma support is **context-only**: the product does not call the Figma API automatically; you get design URLs and optional library paths as context for the agent.

## Example scenarios

- **Implement a screen from a file** — Save the Figma file URL in Marketplace and ask the agent to build or adjust UI components to match frames you describe (layout, typography, spacing).
- **Name alignment** — Ask the agent to rename components, props, or CSS tokens so they line up with layer names in the linked file.
- **Design tokens / theme** — Point `CAIA_FIGMA_LIBRARY_PATH` at exported tokens or a small design-system folder and ask for code updates that consume those values.
- **Copy and microcopy** — Ask the agent to pull wording from the design (as you describe it) into `i18n` files or React strings.
- **Responsive behavior** — Describe breakpoints from the design and ask for CSS or layout changes in the repo.
- **Asset handoff** — With SVGs or icons under the library path, ask the agent to wire them into the app and fix sizing or accessibility attributes.

For **REST automation** (export assets, comments API, etc.), configure a Figma personal access token in **Settings → Agent** and ask for scripts or curl flows explicitly; nothing is fetched from Figma unless you drive it.

## Environment variables

| Variable | Description |
| -------- | ----------- |
| `CAIA_FIGMA_FILE_URL` | HTTPS link to a Figma design file or prototype |
| `CAIA_FIGMA_LIBRARY_PATH` | Optional **workspace-relative** folder (libraries, exported assets, UI kit code) |

Saved from the [Marketplace](../marketplace/) Figma tile. The agent uses these to align copy, spacing, and component naming with your design.

## API access

Automating Figma via REST requires a **personal access token** from Figma’s developer docs. Configure that in **Settings → Agent** (not in Marketplace bookmarks). The model does not receive arbitrary Figma tokens from untrusted sources by design.

[← All integrations](../integrations/)