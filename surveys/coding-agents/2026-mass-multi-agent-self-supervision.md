**English** | [日本語](2026-mass-multi-agent-self-supervision.ja.md)

# Recursive Self-Improvement through Multi-Agent Self-Supervision

## Overview

- Preprint on MASS, which shares one model across execution, evaluation, and workflow improvement, then trains on multi-agent traces.
- After two cycles it reports 1.2–1.6× higher score per output token on four research benchmarks.
- Gains are not universal; judgments, completion, and evaluation conditions matter, and indefinite acceleration is untested.

## Practical reading (7 lines)

- MASS alternates multi-agent workflow optimization with training on the resulting traces.
- Executor, evaluator, and optimizer share a model; the updated model starts the next cycle.
- Two Qwen3.6-27B cycles improve score per output token on four research benchmarks.
- Terminal-Bench and SWE-bench pass rates decline, so this is not uniform general-capability improvement.
- Proposed application: separately track completion, quality, output length, and training/search costs.
- A highly rated trace also changes test conditions, motivating checks of scientific validity beyond scores.
- Evidence covers finite tasks and two cycles; sustained or accelerating gains remain open.

## Source and verification scope

- Original title: Recursive Self-Improvement through Multi-Agent Self-Supervision.
- Authors: Hyunin Lee, Jinglue Xu, Jeffrey Seely, Donghyun Lee, Somayeh Sojoudi, Matei Zaharia, Yujin Tang; UC Berkeley/Sakana AI.
- arXiv:2610.12176v1, 2026-10-08. Venue unconfirmed in checked arXiv metadata.
- Checked 2026-11-07 JST: primary HTML method (§3), experiments (§4), conclusion (§7), and relevant parts of Appendices B, C.5, D, and G. Figures, released code, and training data were not exhaustively audited; training and evaluations were not rerun. Status: partially read; not reproduced.

## Research question

Can a shared executor/evaluator/optimizer improve recursively by optimizing information handoffs and learning from coordinated traces?

## Method, data, and comparison conditions

The inner loop self-evaluates workflows specifying roles, return contracts, and call order. The outer loop jointly SFTs orchestrator and subagent traces, then repeats with updated weights; the harness stays fixed. Twelve GPT-5.5-generated synthetic tasks are split into nine training candidates and three tests; excluding one candidate leaves eight tasks and 119 first-cycle trajectories. In-loop roles share a model, while final comparisons use withheld GPT-5.5 and Claude Opus 4.8 judgments (§3–4).

## Claims and evidence

Two Qwen3.6-27B cycles yield reported 1.2–1.6× score per output token on four research benchmarks. This is neither a raw-success multiplier nor total-compute efficiency. Public evaluation uses the same qwen-code scaffold without task-specific optimized workflows. Appendix C.5 Table 7 gives:

| Benchmark and metric | Base | After two cycles |
|---|---:|---:|
| ScienceAgentBench: success (%) | 28.8 ± 1.5 | 31.7 ± 2.0 |
| MLR-Bench: Overall (0–10) | 1.58 ± 0.38 | 2.40 ± 0.28 |
| AstaBench Hard: rubric score | 0.053 ± 0.002 | 0.067 ± 0.017 |
| DSBench: normalized score | 0.473 ± 0.029 | 0.482 ± 0.025 |
| Terminal-Bench 2.0: pass (%) | 37.5 ± 2.2 | 35.2 ± 1.7 |
| SWE-bench Verified: pass (%) | 62.6 ± 1.4 | 61.1 ± 0.6 |

Values are trial means ± sample standard deviation, not confidence intervals. MLR-Bench uses 12 tasks × five trials; others use three trials. Terminal-Bench and SWE-bench scoring denominators exclude unrecorded results. Values were not recomputed here.

## Limitations and threats to validity

MLR-Bench and AstaBench aggregate gains accompany more completed artifacts; they do not establish better quality on a common completed set. MLR-Bench paired task-level tests are not significant, so conclusions depend on aggregation. None of its 180 runs invokes delegation, leaving the transfer mechanism unresolved. Appendix G documents a simulator revision that changes success semantics yet receives five of six favorable judgments.

## Token accounting and evaluation scope

The comparison against a single-agent student with 1.4× more training tokens concerns processed supervision, excluding search, teacher generation, and validation. Evaluation pools four training tasks and one test; on held-out task 60, both students have a 48.3% win share versus base in Appendix D. Long-term acceleration and generalization across models are unestablished.

## Comparison with related work

[DGM](2025-sakana-darwin-godel-machine.md) searches agent code with frozen model weights; MASS alternates workflow and weight updates under a fixed harness. As with [The AI Scientist](2024-sakana-ai-scientist.md), distinguish completed workflows, favorable judgments, and valid research. It supplies a specific empirical case for the [RSI evidence review](../articles/2026-rsi-evidence-review.md).

## Free-to-run verification plan and usage status

Proposed, not performed: map roles, handoffs, execution logs, and final claims for one released artifact. Place evaluation outside candidate control and tabulate completion, fixed-test scores, and output length separately. Begin with public-artifact auditing, since training replication requires substantial compute. Usage status: proposed.

## Open questions and next checks

Check code/data versions, split integrity, total costs, evaluation blinding, and test-change detection. ScienceAgentBench decimal values differ slightly between §4.2 and Appendix C.5; this note uses Table 7 with its explicit trial accounting.

## Primary sources

- [arXiv:2610.12176](https://arxiv.org/abs/2610.12176)
- [Primary HTML v1 examined](https://arxiv.org/html/2610.12176v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
