**English** | [日本語](2026-unsloth-qwen38-local-inference.ja.md)

# Unsloth Qwen3.8: quantization and local serving

## Overview

- **What it is** Vendor guide for local Qwen3.8 inference, focusing here on the 27B dense model.
- **What it says** It describes GGUF and NVFP4 variants and a November 11 Dynamic V3.1 update.
- **Caveat** Memory and quality claims depend on quantization, context and serving configuration.

## Practical reading (six lines)

- Qwen3.8-27B supports vision and reasoning with a stated 256K context limit.
- The guide lists 16–19 GB for 4-bit variants in total or unified memory units.
- Those figures do not establish peak memory at maximum context and concurrency.
- Dynamic V3.1 quality comparisons use specified context budgets and size conventions.
- NVFP4 instructions target Blackwell hardware; GGUF offers another execution path.
- Proposed application: compare fixed task quality, peak memory and latency before selecting a quant.

## Source and reading scope

Unsloth, Qwen3.8 – How to Run Locally. Checked 2026-11-15 JST; selected 27B requirements, Dynamic V3.1 and execution sections. The page also covers other models, which are outside this note. Mutable documentation; benchmark plots and raw runs not independently audited.

## Evidence and limitations

The main comparison plots exclude embedding-layer sizes; the text separately discusses full disk/RAM usage. Agentic benchmarks use 256K context and others 128K. Treat claimed 5–10% quality improvements as vendor reports with unresolved metric aggregation, not a universal gain.

## Related notes

- [Quantization and coding-agent behavior](../coding-agents/2026-quantization-coding-agent-behavior.md)

## Free check and usage status

Proposed, untried. First make a free inventory of available memory, runtime versions and artifact sizes. Plan a tiny fixed-prompt comparison with identical context and decoding limits, recording correctness, peak RAM/VRAM and time to first token. Next verify model revisions, runtime support and KV-cache overhead. No model download or execution was performed.

## Sources

- [Submitted source](https://unsloth.ai/docs/models/qwen3.8)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
