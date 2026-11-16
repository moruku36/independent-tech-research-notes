**English** | [日本語](2026-aligning-ai-teams-responsibility.ja.md)

# Aligning AI teams: responsibility for the integrated system

## Overview

- **What it is**: A preprint testing whether individual-agent alignment transfers to teams.
- **What it says**: A shared safety specification plus an empowered safety lead is the strongest tested intervention.
- **Caveat**: Claude-only results and remaining task/model gaps limit generalization.

## Practical reading (7 lines)

- The question is who checks and fixes harms in the integrated result.
- Two coding tasks and ten consulting scenarios compare individual agents with teams.
- The coding baseline uses one manager and eight coders; cells have roughly 30 runs.
- Reviews and group chat do not reliably close safety gaps; the compound intervention helps most consistently.
- Proposed use: assign ownership, acceptance evidence and escalation rules before dividing work.
- Proposed evaluation: keep total cost fixed and score both ordinary success and worst-run failures.
- A safety lead is an accountability proposal, not permission to expand an agent's authority.

## Bibliography and reading scope

Siddarth Srinivasan, Morgan Jane Matthews, Jascha Sohl-Dickstein, Erik Jones. *Aligning AI Teams*. arXiv:2611.17820v1, 2026-11-13.

Checked 2026-11-17 JST. Primary HTML §§3–6 and Table 1 checked. Partial reading / not reproduced; appendix, code and annotation protocol not exhaustively audited. Preprint; venue unconfirmed.

- [arXiv record and version history](https://arxiv.org/abs/2611.17820v1)
- [Inspected full text](https://arxiv.org/html/2611.17820v1)
- [DOI](https://doi.org/10.48550/arXiv.2611.17820)

## Method, evidence and limitations

Tasks deliberately oppose safety and business objectives. Responsibility diffusion is supported by behavior annotation and mediation, more clearly in sepsis than recommendation; this is not proof of a universal mechanism. Recommendation retains an approximately 8-point gap for Opus 4.6 under the compound intervention. Consulting uses LLM judging. The synthetic clinical task is not clinical validation. The released framework is [magelab](https://github.com/sidsrinivasan/magelab), not tested here.

## Comparison with related notes

[WorkflowArena](../llm-infrastructure/2026-workflowarena-executable-orchestration.md) evaluates executable orchestration and final acceptance. My proposed connection is to add explicit ownership of cross-module safety invariants to that acceptance contract; the papers do not test the user's Codex/DOTS configuration.

## Free-to-run check and usage status

Proposed, free and unrun: create offline transcripts for a harmless two-module toy program with an integration invariant. Score whether someone tests, discovers, owns and resolves a planted mismatch; compare ordinary review with a named owner and shared specification. A deterministic checker should reject incomplete integration. This checks the evaluation design, not model behavior. Later live comparisons require repeated runs, fixed tasks/models/total budgets and independent grading. No agents were launched and no harness settings changed.

Usage status: proposed / untrialed / not adopted.

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
