**English** | [日本語](2026-fugu-orchestration-report-review.ja.md)

# Fugu: reviewing the product report against its foundations

## Overview

- **What it is** Secondary article explaining Sakana Fugu and its learned-orchestration foundations.
- **What it says** The primary report connects standard Fugu with TRINITY and Fugu-Ultra with the Conductor.
- **Caveat** The July article is historical; product descriptions and benchmark claims are not independent validation.

## Practical reading (six lines)

- Fugu exposes coordinated workers through one model interface.
- The primary report’s standard Fugu selects workers without TRINITY’s three-role assignment.
- It combines supervised initialization with evolutionary optimization.
- Fugu-Ultra extends the Conductor approach to agentic workflows.
- Worker isolation and persistent shared memory are described for Ultra.
- Proposed application: separate fast model routing from deeper delegated workflows in a controlled harness trial.

## Source and reading scope

AI Strategic Insight, 2026-07-06. Checked 2026-11-15 JST. Article partially read and architecture claims checked against Yujin Tang et al., Sakana Fugu Technical Report, arXiv:2606.21228v2 (2026-06-23), selected §3. The official Fugu page confirms both research foundations. This is one combined article/report record.

## Evidence and limitations

TRINITY’s three roles should not be copied into a description of standard Fugu unchanged. The July two-variant description is dated: the official page checked in November lists four variants. Reported superiority depends on benchmark and comparison setup; the full benchmark table, current pricing, export-control anecdotes and corporate-finance claims were not independently audited. The primary table also uses provider-reported baselines where available.

## Related notes

- [TRINITY](2025-trinity-evolved-coordinator.md)
- [Conductor](2025-conductor-natural-language-orchestration.md)
- [RIVET routing](2026-rivet-multiturn-llm-routing.md)

## Free check and usage status

Proposed, untried. Make a free offline matrix of model selection, subtask generation, shared state, verification, total calls and latency. Plan a small matched-budget comparison of single routing, sequential role routing and explicit workflows, each with external tests. Next inspect benchmark protocols, data-routing restrictions and failure handling before product adoption. No service signup or API request was made.

## Sources

- [Submitted source](https://aistrategicinsight.com/blog/news/2026-07-06-sakana-ai-fugu-orchestration-llm-competition/)
- [Inspected text](https://arxiv.org/html/2606.21228v2)
- [Sakana Fugu](https://sakana.ai/fugu/)
- [arXiv:2606.21228v2](https://arxiv.org/abs/2606.21228v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
