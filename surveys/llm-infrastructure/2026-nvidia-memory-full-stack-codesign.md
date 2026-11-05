**English** | [日本語](2026-nvidia-memory-full-stack-codesign.ja.md)

# NVIDIA's memory hierarchy and full-stack codesign

## Overview

- Vendor technical article on managing inference memory across GPU, CPU, storage, and software.
- NVIDIA describes quantization, tiered KV caching, and RAG index placement, and reports throughput-per-dollar gains for a specific workload.
- The comparisons depend on vendor-selected conditions and do not guarantee general operating savings.

## Practical reading (7 lines)

- Long agent workflows put model weights and KV cache in competition for HBM.
- The article describes NVFP4 weights and distribution across NVL72 to free HBM.
- Idle KV cache moves to CPU memory or CMX storage and returns for reuse.
- RAG indexes remain outside HBM, with only retrieved passages entering context.
- For a specified SemiAnalysis AgentX workload, it cites up to 30× throughput per dollar for Vera Rubin NVL72 versus GB300 NVL72.
- Operators should measure bandwidth, latency, cache movement, power, and HBM capacity together.
- This note has not independently benchmarked the vendor's cost and performance claims.

## Source and verification scope

Amr Elmeleegy, NVIDIA Blog, 2026-11-05. Specified article checked on 2026-11-06 JST. Vendor article, not a peer-reviewed paper; no reproduction.

## Method, claims, and evidence

The article combines NVFP4 and distributed weights, compressed and offloaded KV cache, system-wide reuse, and RAG indexes outside HBM. It cites a SemiAnalysis AgentX DeepSeek V4 Pro workload at 125 tokens/s/user to compare Vera Rubin NVL72 throughput per dollar with GB300 NVL72.

## Limitations and open questions

The discussion centers NVIDIA products. The up-to-30× result is specific to the named workload and service-level condition. Measurement and pricing assumptions were not independently audited here.

## Comparison with related notes

Unlike RIVET's model routing, this article focuses on managing the memory hierarchy.

## Low-cost verification plan and use status

Proposed, not performed: measure HBM occupancy, cache hit rate, latency, and cost by workload in a small inference setup.

## Primary source

- [Specified primary source](https://blogs.nvidia.com/blog/memory-full-stack-codesign/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
