**English** | [日本語](2026-dlite-history-free-speculation.ja.md)

# DLite and history-free speculative decoding

## Overview

- **What it is** Speculative-decoding research for long agent interactions.
- **What it says** DLite uses target-model hidden states and a lightweight sequential head to draft tokens without retaining the draft model’s historical context.
- **Caveat** History-free describes the drafting component. Results depend on model, workload and serving setup.

## Practical reading (six lines)

- A small drafting component proposes tokens for target-model verification.
- Target hidden states supply information from the accumulated context.
- Two-stage training combines parallel prediction with a sequential head.
- The paper reports acceptance length and measured decoding speed separately.
- A proposed inference study records latency and memory as context and concurrency grow.
- The target model still handles context, so the design’s state requirements need component-level accounting.

## Source and reading scope

Jiaming Xu, Hanzhen Wang, Tianlang Zhao, Jiewen Xiao, Chengze Yuan, Jiayi Pan, Yongkang Zhou, Jiancai Ye, Yu Wang and Guohao Dai. arXiv:2610.23787v1, 2026-10-16. Checked 2026-11-13 JST. Selected §§4–5 and Tables 1–4 read.

## Method, evidence and limitations

Experiments use Qwen3-4B and Qwen3-8B on general, long-context and agent workloads. Table 3 separates speedup from accepted draft length. These measurements concern inference behavior. Agent task accuracy and whole-workflow cost need separate assessment.

## Related notes

- [Cache engineering for agents](2026-cache-engineering-for-agents.md)

## Free check and usage status

Proposed, untried. Define fixed prompts and output checks, then plan matched context-length and concurrency sweeps. Record accepted tokens, time, memory and output agreement together. Next inspect implementation, model-specific training and the speedup baseline before running a comparison.

## Primary sources

- [Versioned record](https://arxiv.org/abs/2610.23787v1)
- [Inspected full text](https://arxiv.org/html/2610.23787v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
