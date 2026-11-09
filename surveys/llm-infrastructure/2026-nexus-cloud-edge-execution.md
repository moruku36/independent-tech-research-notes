**English** | [日本語](2026-nexus-cloud-edge-execution.ja.md)

# Nexus: persistent execution and authority across devices

## Overview

- **What it is**: A cloud-edge execution fabric for agents.
- **What it says**: Persistent identities connect device authority, recovery and results.
- **Caveat**: Controlled tests do not prove universal exactly-once effects.

## Practical reading (six lines)

- The unit of work is a persistent invocation.
- Run-scoped delegation limits operations on selected devices.
- Recorded outcomes support recovery without needless replay.
- Our proposal: separate logical work, attempts and observation.
- Free check: simulate a crash around a result commit.
- Missing records must not imply an action never happened.

## Bibliography and verification scope

Cary Chang and Jialin Zhou; arXiv:2610.05709v1, 2026-10-05. Systems preprint; venue unconfirmed.

Checked 2026-11-10 JST. Primary HTML design §4 and evaluation setup §5.1 partially read, with abstract results. Full appendix, code and reproduction unverified.
Status: primary source checked / partially read / not reproduced.

## Question, method, claims and evidence

An OpenWrt edge runtime complements cloud/device services. A journal cannot resolve an external effect completed before its result was committed. Reported cross-device/revocation tests are small; Dify/Dapr comparisons have workload-specific controls and trade-offs, not a universal ranking.

## Comparison with related work

Keep execution lifecycle separate from how an agent decomposes reasoning. [Related note](2026-recursive-multi-agent-systems.md)

## Free check plan, usage status and next checks

For DOTS/Codex research, give each job stable identity, a bounded lease and explicit reconciliation. Free check: design fake append/receipt cases with before/after-commit failure; no real device access. Proposed only. Next: inspect reproducibility artifacts and endpoint-side idempotency.

## Primary sources

- [Requested source](https://arxiv.org/abs/2610.05709)
- [Inspected version](https://arxiv.org/html/2610.05709v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
