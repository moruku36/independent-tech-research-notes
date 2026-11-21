**English** | [日本語](2026-thinking-machines-inkling-2-mini.ja.md)

# Inkling 2 Mini: looped inference and local deployment

## Overview

- **What it is**: Thinking Machines Lab’s release of an open-weight, looped mixture-of-experts Transformer.
- **What it says**: The released model applies its middle layers three times per token, with 48.2% reported on DeepSWE v1.1. A separate research checkpoint tests how results vary with pass count.
- **Caveat**: The published speed frontier uses a theoretical ceiling. The monitorability experiments cover specific checkpoints, tasks, and measures.

## Practical reading (six lines)

- Inkling 2 Mini has 26.4B stored parameters, with 3.4B active and 5.4B weight activations per token when the repeated passes are counted.
- The model card lists Apache 2.0 and an approximately 20 GB mixed-precision checkpoint. The supported Apple silicon configuration starts at 32 GB of memory.
- Thinking Machines reports 48.2% on DeepSWE v1.1 and 71.6% on Terminal-Bench v2.1 under the stated harnesses. The plotted speed frontier is theoretical.
- In a separate variable-loop model, the estimated 50% success horizon without written reasoning rose from 16 to 37 seconds of human task time between one and three passes.
- On GPQA Diamond items answered correctly at every tested pass count, written reasoning shortened while simple readability proxies held steady. Those proxies measure surface properties of the text.
- Proposed application: use fixed benign tasks to compare accepted answers, elapsed time and peak memory on the same device.

## Sources and reading scope

Thinking Machines Lab, November 20, 2026. Checked the release, architecture and selected evaluation sections, and the model card on November 22, 2026 JST. Benchmark reproduction, model use and local hardware measurements remain unperformed.

## Evidence and limitations

- **Architecture and deployment.** The model stores 24 layers and applies 48 layers’ worth of computation per token, repeating the middle blocks with shared weights. Twenty layers use NVFP4 and the final four use MXFP8. The approximately 20 GB figure describes the checkpoint. Actual working memory also depends on context length and the runtime. The release supports local Apple silicon execution via Ollama and lists DGX Spark separately.
- **Capability and speed.** The DeepSWE score uses mini-swe-agent v2.4.6, and Terminal-Bench v2.1 uses Pi v0.83.0 for Inkling 2 Mini. The release warns that comparison setups vary across models. The decoding chart assumes 614 GB/s memory bandwidth, BF16 weights and batch size one. This ceiling gives a hardware-model estimate, while local latency depends on the deployment and workload.
- **Variable loops and monitoring.** The 16-to-37-second result comes from a subset of Think Fast tasks, with the horizon expressed in human completion time at fitted 50% success. The horizon roughly levels off after three passes, while one serial lookup task improves out to ten. In the always-correct GPQA Diamond subset, mean reasoning tokens fell from 3,703 to 1,661 between one and five passes, with similar sentence length and dictionary coverage. These measures cannot establish whether traces reflect the internal computation. The separate agent monitoring evaluation reports no clear trend with pass count in the tested setting.

## Application and free check

Proposed. Prepare a small, fixed set of code-understanding and deterministic document tasks. Start with a local scorecard for exact correctness, wall-clock time, peak memory, context length and runtime. With compatible hardware, later compare models on the same tasks and score complete answers. Any conclusions about pass count require the variable-loop checkpoint.

## Related notes

- [Qwen3.8 local inference](2026-unsloth-qwen38-local-inference.md)
- [Quantization and coding-agent behavior](../coding-agents/2026-quantization-coding-agent-behavior.md)

## Sources

- [Release article](https://thinkingmachines.ai/news/inkling-2-mini/)
- [Model card](https://thinkingmachines.ai/model-card/inkling-2-mini/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
