**English** | [日本語](2025-sakana-adaptive-branching-mcts.ja.md)

# Wider or Deeper? Scaling LLM Inference-Time Compute with Adaptive Branching Tree Search

## Overview

- Research article and associated paper on adaptively generating new candidates or refining existing solutions.
- AB-MCTS allocates search using external scores and Thompson sampling; Multi-LLM also selects the model.
- ARC-AGI-2 Pass@250 candidate coverage differs substantially from selecting two final answers for Pass@2.

## Practical reading (7 lines)

- AB-MCTS chooses whether to generate a new solution or refine an existing one.
- External scores and Thompson sampling guide the next branch.
- Multi-LLM also chooses which model performs the next generation.
- On 120 ARC-AGI-2 tasks with up to 250 generations, it reports finding correct candidates for over 30%.
- A preliminary two-final-answer selection achieves 19.2%, exposing the gap between finding and selecting.
- Proposed application: compare independent sampling, refinement, and search under the same budget, evaluating actual submissions.
- Results depend on evaluator quality, prices, and latency; no method wins every condition.

## Source and verification scope

- Supplied article: Inference-Time Scaling and Collective Intelligence for Frontier AI, Sakana AI, 2025-07-01.
- Associated paper: Wider or Deeper? Scaling LLM Inference-Time Compute with Adaptive Branching Tree Search. Yuichi Inoue, Kou Misaki, Yuki Imajuku, So Kuroki, Taishi Nakamura, Takuya Akiba.
- arXiv:2503.04412v5, 2025-11-07; first submission 2025-03-06. The arXiv comments report NeurIPS 2025 spotlight acceptance; venue-side confirmation not checked.
- Checked 2026-11-07 JST: article text and primary HTML method, Table 1, limitations, and Appendix D Multi-LLM/ARC-AGI-2 evaluation, partially. TreeQuest and experiment code not executed. Status: partially read; not reproduced.

## Research question

How should inference budgets be allocated among new candidates, refinement, and different models?

## Method, data, and comparison conditions

AB-MCTS adapts tree width and depth with external feedback and Thompson sampling. It compares with repeated sampling, sequential refinement, and standard MCTS. Multi-LLM adds model selection; ARC-AGI-2 examples combine o4-mini, Gemini-2.5-Pro, and DeepSeek-R1-0528.

## Claims and evidence

On 120 public ARC-AGI-2 tasks with at most 250 generations each, reported correct-candidate coverage is about 23% for o4-mini repeated sampling, 27.5% for AB-MCTS, and over 30% for Multi-LLM (article; Appendix D). These are Pass@250 search results. A simple two-answer selector achieves preliminary Pass@2 of 19.2%. Repeated sampling leads the paper's Table 1 ARC-AGI conditions; AB-MCTS is not best everywhere.

## Limitations and threats to validity

Reliable external scores are assumed. Fit to demonstrations does not ensure test correctness, and finding a correct candidate does not ensure selecting it. Equal call counts do not imply equal token costs or latency. Results depend on historical models and workloads. Distinguish the article's initial ARC-AGI-2 results from other paper benchmarks.

## Comparison with related work

[RIVET](2026-rivet-multiturn-llm-routing.md) learns turn-level model selection; AB-MCTS searches candidate solutions with feedback. [Minimal ML harnesses](../coding-agents/2026-ml-engineering-minimal-harness.md) motivates measuring added search under matched conditions. These are conceptual comparisons, not direct experiments.

## Free-to-run verification plan and usage status

Proposed, not performed: separately tabulate best-candidate and selected-submission scores from public traces. Any toy experiment should fix generation and submission budgets and use only available free resources. Usage status: proposed.

## Open questions and next checks

Check implementation versions, scoring and final-selection rules, and comparisons matched by money, tokens, and latency.

## Primary sources

- [Supplied research article](https://sakana.ai/ab-mcts/)
- [Associated paper metadata](https://arxiv.org/abs/2503.04412)
- [Paper version examined](https://arxiv.org/html/2503.04412v5)
- [Released code (not executed)](https://github.com/SakanaAI/treequest)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
