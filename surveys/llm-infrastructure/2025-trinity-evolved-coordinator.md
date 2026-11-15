**English** | [日本語](2025-trinity-evolved-coordinator.ja.md)

# TRINITY: learned model and role selection

## Overview

- **What it is** Research on a compact coordinator for heterogeneous LLMs.
- **What it says** A hidden-state head selects a model and one of three roles over multiple turns.
- **Caveat** Reported gains depend on worker pool, evaluation budget and benchmark version.

## Practical reading (six lines)

- A Qwen3-0.6B backbone supplies contextual representations.
- A roughly 10K-parameter head selects Thinker, Worker or Verifier plus a worker model.
- Singular-value scales and the head form a small trainable parameter set.
- Sep-CMA-ES optimizes coordination using end-task feedback.
- The reported LiveCodeBench pass@1 is 86.2% on the specified January–April 2025 slice.
- Proposed application: evaluate bounded planner/worker/verifier routing against a matched fixed workflow.

## Source and reading scope

Jinglue Xu, Qi Sun, Peter Schwendeman, Stefan Nielsen, Edoardo Cetin and Yujin Tang. TRINITY: An Evolved LLM Coordinator. arXiv:2512.04695v3, 2026-04-27; first posted 2025-12-04. Checked 2026-11-15 JST, selected §§2–4. ICLR 2026 status is reported in the metadata; older-version differences unexamined.

## Evidence and limitations

The main setup uses seven workers, up to five turns and adjusted output-token budgets for comparisons. Verification acceptance is a model judgment, not a proof of correctness. Evolutionary training still consumes worker calls; lightweight trainable parameters do not imply negligible total cost.

## Related notes

- [Conductor](2025-conductor-natural-language-orchestration.md)
- [Fugu report review](2026-fugu-orchestration-report-review.md)
- [Agent scaling](2025-scaling-agent-systems.md)

## Free check and usage status

Proposed, untried. First make a free offline routing ledger with role contracts, stopping rules and external acceptance tests. A later local comparison should fix worker pool, task set and total budget across fixed and adaptive routing. Record task success, verification errors, calls and latency. Next inspect checkpoints, training artifacts and evaluation splits before attempting the learned coordinator; no training or model calls were run.

## Sources

- [Submitted source](https://arxiv.org/abs/2512.04695v3)
- [Inspected text](https://arxiv.org/html/2512.04695v3)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
