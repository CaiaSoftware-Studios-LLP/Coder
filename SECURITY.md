# Security Policy

**Caia Coder** is a **subscription product**. This GitHub repository hosts **documentation and community channels**—not the private application source. Security reports are handled by our security team regardless of where you file them.

## Scope

Reports should cover security issues in:

- The **Caia Coder** hosted service and subscriber-facing applications
- **Official** Caia-operated infrastructure described in public documentation
- **This repository** (e.g. malicious content in docs or workflow definitions)

Out of scope: issues in third-party model providers, your own API keys stored in BYOK/BYOM, or vulnerabilities in your self-hosted environment configuration unless they stem from Caia Coder product behavior.

## Supported versions

Security fixes are applied to **currently supported** Caia Coder deployments (SaaS and supported self-hosted releases). We do not publish version tags for private application code in this repo; see [CHANGELOG.md](CHANGELOG.md) for user-facing release notes.

| Channel | Support |
| ------- | ------- |
| **Caia SaaS** (production) | Supported — fixes rolled out by Caia |
| **Self-hosted** (Enterprise / operator) | Supported per your agreement; contact your account team for patch guidance |
| **Older releases** | Not supported unless covered by a maintenance agreement |

## Reporting a vulnerability

**Do not** report security vulnerabilities through public GitHub Issues or Discussions.

Email **security@caiaplatform.com** with:

1. Description of the issue and potential impact  
2. Steps to reproduce (proof of concept if available)  
3. Affected surface (SaaS URL, self-hosted, account portal, etc.)  
4. Your contact information for follow-up  

We will:

- **Acknowledge** receipt within **one business day**
- Provide **status updates** as we investigate
- Notify you when a fix is deployed or mitigations are in place (subject to coordinated disclosure)

Please allow us reasonable time to remediate before public disclosure. We support coordinated disclosure for valid reports.

## Safe harbor

We support good-faith security research on Caia Coder systems within the rules above. Do not access other users’ data, disrupt production, or exceed the minimum steps needed to demonstrate a vulnerability.

## Billing, privacy, and legal

- **Privacy:** https://coder.caiaplatform.com/privacy  
- **Terms:** https://coder.caiaplatform.com/terms-of-service  
- **General support:** [SUPPORT.md](SUPPORT.md)
