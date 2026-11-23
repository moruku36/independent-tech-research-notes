**English** | [日本語](2026-adaoffload-multi-gpu-moe.ja.md)

# AdaOffload: adaptive CPU–GPU execution for MoE inference

## Overview

- **What it is**: A preprint on running large mixture-of-experts models with some expert weights in host memory.
- **What it says**: AdaOffload chooses how much work to execute on CPUs or transfer to GPUs using hardware profiles and observations of the current workload.
- **Caveat**: The performance ratios depend on model, concurrency, hardware topology, and comparison runtime.

## Practical reading (six lines)

- The scheduler profiles computation and transfer costs, including contention when CPUs and GPUs work together.
- CPU and GPU tensor sharding are separate. The CPU layout accounts for NUMA memory locality.
- Decode adjusts how many active experts to fetch for GPU execution. Prefill can instead overlap next-layer weight transfers with current computation.
- Across four machines on DeepSeek-V4-Flash AIME tasks, mean per-request decode rate was 1.30×, 1.88× and 2.47× the strongest tested baseline at concurrency 1, 4 and 8.
- Mean time to first token fell by 41%, 57% and 67% in the same comparison. Tail latency and aggregate capacity require their own measurements.
- Proposed use: compare two runtimes at the same cache budget and report both the full latency distribution and throughput.

## Source and reading scope

William X. Zheng, Zhongjie Chen, Shuo Yang and colleagues, *Multi-GPU MoE Inference with Adaptive Expert Offloading*, arXiv v1, November 6, 2026. Checked Sections 3–4, Figures 7–9, and selected setup details on November 24, 2026 JST. No installation or replication was performed.

## Evidence and limitations

- **Execution policy.** Offline profiles estimate expert compute and transfer costs under contention. Runtime sampling tracks the load routed to experts and their cache residency. During decode, the system balances CPU execution against GPU transfers and computation. During prefill, the system can choose between hybrid execution and prefetching the next layer’s expert weights.
- **Comparisons.** The main DeepSeek-V4-Flash setup uses the same MXFP4 checkpoint and expert-cache budget for AdaOffload, llama.cpp, KTransformers, and Ollama. Figure 7 gives the four-platform AIME result by concurrency. The abstract’s 1.9–15.5× range summarizes reasoning results across three MoE models and five platforms. The detailed comparisons vary by setup, including later GLM runs and some coding baseline sessions that hit the timeout.
- **Reading the metrics.** Decode rate here is average tokens per second per request, and TTFT is mean time to the first token. GPU count alone is an incomplete description of a testbed. Host bandwidth, PCIe topology, available memory, and input and output length all matter.

## Application and free check

Proposed. On an available host, use the same local checkpoint, quantization, cache budget and prompts for each runtime. Record per-request decode rate, aggregate output rate, first-token latency percentiles, allocated memory, and timeout counts at several concurrency levels.

## Related note

- [Serving on heterogeneous GPUs](2025-heterogeneous-gpu-llm-serving.md)

## Sources

- [arXiv record](https://arxiv.org/abs/2611.10219)
- [Inspected v1 text](https://arxiv.org/html/2611.10219v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
