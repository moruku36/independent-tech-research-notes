**English** | [日本語](2026-parallact-shared-code-coordination.ja.md)

# ParallACT: coordinating independent requests in shared code

## Overview

- **What it is** Benchmark of two coding agents handling separate requests in a shared repository.
- **What it says** Independent parallel work often loses joint correctness; a sequential handoff recovers much of the gap.
- **Caveat** Tasks are selected to require coordination, and the single-agent oracle receives both requirements.

## Practical reading (six lines)

- ParallACT includes complementary and contradictory requirement pairs.
- Success checks the combined patch against integration or joint tests.
- For Claude Opus 4.8, contradictory success is 62% for the oracle versus 16% for unaware parallel agents.
- Messaging reaches 20% in that comparison; a sequential handoff reaches 54%.
- These are diagnostic conflicts, not an estimate of conflict frequency in ordinary development.
- Proposed application: track interface ownership, shared assumptions and both requirements in merge acceptance tests.

## Source and reading scope

Rishabh Mediratta, Lingyun Xiao, Peter Stone, Joydeep Biswas and Elias Stengel-Eskin, *Decentralized Multi-Agent Coordination and Communication in Shared Codebases*. arXiv:2611.00314v1, 2026-10-30. Checked 2026-11-14 JST, selected §§2–4, Tables 1–2, evaluation-set and limitations passages. Venue unconfirmed.

## Method, evidence and limitations

Claude Code/Opus uses 85 instances, including 50 contradictory pairs; six open-weight/harness configurations use 155. Within-configuration comparisons use the same instances. Effective token cost is relative to each oracle; cross-configuration subsets and cost conventions matter. Results cover two agents and a small targeted dataset.

## Related notes

- [Agent-system scaling](../llm-infrastructure/2025-scaling-agent-systems.md)
- [Scion source control](2026-anthropic-scion-source-control.md)

## Free check and usage status

Proposed, untried. Create a free toy repository with two independent change requests and tests covering their combined behavior. Plan sequential and parallel variants, recording interface decisions, ownership messages, integration failures, tokens and time. Keep requirements and tests fixed and mark when an agent sees both requests. Next inspect benchmark construction and the cost definition before estimating gains for the current harness.

## Sources

- [Versioned record](https://arxiv.org/abs/2611.00314v1)
- [Inspected text](https://arxiv.org/html/2611.00314v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
