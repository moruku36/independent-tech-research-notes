**English** | [日本語](2026-chatgpt-wallet-agentic-payments.ja.md)

# ChatGPT Wallet: purchase approval and payment tokens

## Overview

- **What it is** Official announcement of agent-assisted card payments through ChatGPT Wallet.
- **What it says** Users review and approve each purchase; payment networks provide substitute credentials.
- **Caveat** Initial rollout is limited. Parameter-based advance delegation is described as a future direction.

## Practical reading (six lines)

- The user checks items, total and selected card before a security check.
- The agent and merchant receive payment-token credentials rather than actual card details.
- Initial availability is in dots for US Pro subscribers aged 18+ with eligible US-issued cards.
- The merchant retains order fulfillment, customer service and fraud decisions.
- Official guidance says existing checkout forms work without a Wallet-specific integration.
- Proposed application: bind approvals to an exact order and keep payment credentials outside research-agent memory.

## Source and reading scope

OpenAI, *Introducing ChatGPT Wallet*, 2026-11-13. Checked 2026-11-14 JST. Announcement purchase flow and availability, plus official OpenAI documentation on accepting payments, read. Account eligibility and live checkout were not tested.

## Evidence and limitations

Security and compatibility statements are provider claims. Official payment guidance forbids reusing the credential for a separate purchase; recurring billing needs specific consent. Delegation by spending/category/time parameters remains a stated plan. Browser access and payment-risk checks can still cause declines.

## Related notes

- [Human approval boundaries](../agent-safety/2026-inalienable-human-approval.md)
- [Three pillars of oversight](../security-governance/2026-three-pillar-agent-oversight.md)

## Free check and usage status

Proposed, untried. Use a free mock checkout with fictitious items and credentials. Record the exact order, amount, approval, expiry and cancellation state, then test changed totals and duplicate actions against the approval record. Treat this as harness design research, not a Wallet integration. Next verify documented transaction binding, eligibility and risk-provider behavior before any implementation; no card, payment or account setup was performed.

## Sources

- [Submitted announcement](https://openai.com/ja-JP/index/introducing-chatgpt-wallet/)
- [Official payment guidance](https://developers.openai.com/commerce/guides/accept-payments)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
