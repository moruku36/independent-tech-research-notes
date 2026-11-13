**English** | [日本語](2026-camp-ii-file-memory-distillation.ja.md)

# CAMP-II: learning file-based memory across context boundaries

## Overview

- **What it is** Post-training research on preserving task state through ordinary file operations.
- **What it says** CAMP-II distils a frozen teacher’s guidance into a policy that writes and rereads workspace memory.
- **Caveat** This requires weight training; adding a note file to an existing API harness has not reproduced its gains.

## Practical reading (six lines)

- CAMG-II covers Shop, Coding, AutoResearch, General and Visual tasks.
- An episode-persistent workspace survives replacement of active context.
- Asynchronous on-policy distillation supervises the student’s own sampled tokens.
- The 4B mean is 64.6%, versus frozen 45.3% and the strongest OPD baseline’s 51.8%.
- The reported 2.97× compares improvements above the frozen student, not raw success rates.
- Proposed application: test structured continuation files and readback checks in the current harness.

## Source and reading scope

Lirui Luo et al., *Coding Agent Memory Post-Training II: Unlocking the Memory Potential of Pre-trained File Operations for Long-Horizon Tasks via On-Policy Distillation*. arXiv:2611.14009v2, 2026-11-12; first posted 2026-11-10. Checked 2026-11-14 JST, selected §§4–7 and Table 1. Venue and version differences unconfirmed.

## Method, evidence and limitations

Table 1 implies (64.6 − 45.3)/(51.8 − 45.3) ≈ 2.97. Evaluation uses 128 tasks per domain and network-free subsets of two external benchmarks. Students are Qwen3.5-4B/9B with one frozen teacher; larger-scale and multi-teacher transfer remain untested.

## Related notes

- [Agent memory components](../llm-infrastructure/2026-anthropic-agent-memory-components.md)
- [OpenClaw Dreaming](../llm-infrastructure/2026-openclaw-dreaming-memory-consolidation.md)

## Free check and usage status

Proposed, untried. Begin with a free offline task-state template containing decisions, evidence, pending tests and exact artifact paths. Plan a small local comparison of bounded summaries and file readback under identical context limits, scoring recovered facts and task outcomes separately. Training replication needs additional compute and model access and is outside this note. Next inspect contamination, reset conditions, training cost and released implementation before claiming equivalent results.

## Sources

- [Versioned record](https://arxiv.org/abs/2611.14009v2)
- [Inspected text](https://arxiv.org/html/2611.14009v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
