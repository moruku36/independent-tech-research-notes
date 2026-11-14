**English** | [日本語](2026-glm53-two-dgx-stations.ja.md)

# GLM-5.3 across two DGX Stations: capacity and concurrency

## Overview

- **What it is** NVIDIA tutorial for serving GLM-5.3 NVFP4 on two GB300 DGX Stations.
- **What it says** Tensor parallelism and RDMA split the model across two GPUs behind one endpoint.
- **Caveat** The reported benchmark is workload-specific and is not an end-to-end agent success evaluation.

## Practical reading (six lines)

- The checkpoint is about 464 GB; activated parameters do not determine total weight storage.
- TP=2 distributes computation; the GPU memories remain distinct.
- The example disables CPU weight offload and enables FP8 KV cache, prefix caching and MTP.
- Aggregate output peaks at 607.8 tok/s at configured concurrency 16.
- At concurrency 32, output falls to 385.0 tok/s and mean latency reaches 453.54 seconds.
- Proposed application: select concurrency using latency and per-user throughput as well as total output.

## Source and reading scope

Fatima Fall, NVIDIA Technical Blog, 2026-11-13. Checked 2026-11-15 JST; introduction, prerequisites, serving design and Table 2 inspected. AI-generated summary was checked against body text. Deployment and model-card audit not performed.

## Evidence and limitations

Table 2 uses SPEED-Bench Coding, four MTP draft tokens, FP8 KV cache and prefix caching, excluding warmup. Mean TTFT can end at a reasoning token. Aggregate throughput differs from per-user decoding rate. Results do not establish cost efficiency or quality for other prompts.

## Related notes

- [Self-hosted inference and API costs](2026-shattered-self-hosted-llm-vs-api.md)

## Free check and usage status

Proposed, untried. Start with a free workload sheet fixing input/output lengths, latency targets and concurrent users. If existing hardware permits, later plan a small concurrency sweep with measured memory, RDMA health, TTFT and output validation. Next inspect licenses, exact software versions and reproducible prompts. No equipment purchase, container launch or benchmark run was performed.

## Sources

- [Submitted source](https://developer.nvidia.com/blog/when-one-gpu-isnt-enough-serving-glm-5-3-across-two-nvidia-dgx-stations-with-vllm/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
