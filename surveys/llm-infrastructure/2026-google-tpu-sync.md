**English** | [日本語](2026-google-tpu-sync.ja.md)

# TPU Sync: moving KV cache and model weights

## Overview

- **What it is**: A TPU model-state transport library.
- **What it says**: Coordinates cache/weight movement across memory tiers and hosts.
- **Caveat**: Inference claims and experimental RL/storage features differ.

## Practical reading (six lines)

- Long contexts can make state movement a bottleneck.
- Native-layout asynchronous DMA overlaps transfer and compute.
- The reported latency gains depend on workload and hardware.
- Our proposal: track transfer, recomputation and cache hit rate.
- Free check: draw the state-movement critical path.
- Do not confuse this cache with semantic agent memory.

## Bibliography and verification scope

Fenghui Zhang and Weiren Yu, Google Cloud, 2026-11-09; vendor technical article.

Checked 2026-11-10 JST. Primary text returned by search checked: architecture, inference/RL distinction and performance footnote. Direct open failed; repository, wheels and benchmarks not run.
Status: primary source checked / partially read / not reproduced.

## Question, method, claims and evidence

The footnote describes internal July 2026 testing on TPU v7x with a specified serving stack. RL transfer primitives and secondary-storage tiering include experimental features. We did not independently validate performance or integrations.

## Comparison with related work

Compare the memory-hierarchy design question, not hardware-vendor benchmark numbers. [Related note](2026-nvidia-memory-full-stack-codesign.md)

## Free check plan, usage status and next checks

For an infrastructure study, freeze tensor layout, topology and cache reuse before comparing TTFT. Free check: build a measurement checklist from the article without buying TPU time. Proposed only. Next: inspect the linked implementation/version, correctness tests and full measurement boundary.

## Primary sources

- [Requested source](https://cloud.google.com/blog/topics/ai-infrastructure/introducing-tpu-sync-fast-kv-cache-and-weight-transfer-on-tpu?hl=en)
- [Canonical article URL](https://cloud.google.com/blog/topics/ai-infrastructure/introducing-tpu-sync-fast-kv-cache-and-weight-transfer-on-tpu)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
