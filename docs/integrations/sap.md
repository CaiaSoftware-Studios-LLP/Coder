---
layout: docs
title: SAP
permalink: /integrations/sap/
---

Marketplace **SAP** fields inject **landscape and module scope** so the agent reasons in the correct ERP context (FI, CO, MM, SD, HCM, PP, QM, PM, Basis, ABAP, HANA, Security, etc.).

## Example scenarios

- **OData integration draft** — Ask for sample requests, headers, and entity sets against your saved gateway/Fiori base URL (documentation and code stubs in the workspace).
- **Module-specific logic** — With `CAIA_SAP_MODULES_FOCUS` set (e.g. MM, SD), ask for field mappings, IDoc outlines, or validation rules phrased in that module’s vocabulary.
- **Interface spec** — Describe BAPI/RFC vs OData constraints; ask for an interface document and error-handling notes tailored to your SID and client.
- **Testing notes** — Ask for test cases for a user story that touches a given client and system ID, including authorization objects to watch for.
- **Troubleshooting checklist** — Ask for a structured checklist (connectivity, SSL, user lock, RFC destination) when you paste error messages into the chat.
- **Security / segregation of duties** — High-level guidance on roles and sensitive transactions, always to be validated by your Basis/security team.

The agent does **not** bypass SAP authorization; treat outputs as drafts for your functional and security review.

## Environment variables (representative)

These variables can be bound in the local vault when you prefer not to store passwords in the browser:

| Variable | Description |
| -------- | ----------- |
| `CAIA_SAP_ODATA_BASE_URL` | HTTPS base for OData / Fiori |
| `CAIA_SAP_HOST` / `CAIA_SAP_PORT` | Gateway or app server |
| `CAIA_SAP_USER` / `CAIA_SAP_PASSWORD` | HTTP/OData credentials (password often in [vault](../local-vault/)) |
| `CAIA_SAP_SYSTEM_ID` | SID |
| `CAIA_SAP_CLIENT` | Client (Mandant) |
| `CAIA_SAP_MODULES_FOCUS` | Comma-separated module emphasis, e.g. `FI,MM,SD` |

## Usage

Use the [Marketplace](../marketplace/) to bookmark the landscape, then **Save**. Combine with explicit instructions for OData calls, notes, or command-line SAP/OData clients where appropriate.

[← All integrations](../integrations/)