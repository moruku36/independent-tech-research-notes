**English** | [日本語](2026-llms-cloud-architecture-orchestration-survey.ja.md)

# LLMs in Cloud: A Discussion on Architecture, Orchestration, and Inference

## Overview

- Survey preprint spanning accelerator sharing, scheduling, inference, resilience, and confidentiality.
- It connects prefill/decode separation and tiered KV caching with latency, cost, throughput, and confidentiality trade-offs.
- Selection descriptions are inconsistent; neither its reported 133-study corpus nor cited performance values were independently validated here.

## Practical reading (7 lines)

- This survey offers a map from GPU resources to cluster operations for LLM serving.
- It distinguishes compute-heavy prefill from memory-bandwidth-heavy decode.
- It relates continuous batching, KV caching, serverless cold starts, fault tolerance, and TEEs.
- The authors report a PRISMA-guided 133-study synthesis, but selection descriptions are inconsistent.
- Proposed application: compare TTFT, inter-token latency, cost, recovery, and confidentiality for candidate designs.
- Return to original workloads and measurement conditions before using cited improvements.
- Use the survey to find further reading; it is not a common benchmark of current production systems.

## Source and verification scope

- Original title: LLMs in Cloud: A Discussion on Architecture, Orchestration, and Inference.
- Authors: Jannatun Noor, Athar Noor Mohammad Rafee, Md. Sadman Haque, Sreezon Das Gupta, Atiar Osman, Md. Abu Obaida Zishan.
- arXiv:2610.33475v1, 2026-10-24; venue unconfirmed in checked arXiv metadata.
- Checked 2026-11-07 JST: primary HTML methods (§3), taxonomy and main discussion, and limitations (§7.3), partially. Some HTML cross-references are malformed. Cited papers, all figures, and search results were not independently audited. Status: partially read.

## Research question

How should accelerator virtualization, orchestration, inference, resilience, and confidentiality be combined to meet cloud LLM service requirements?

## Method, data, and comparison conditions

The authors describe four database searches over January 2020–February 2026 and qualitative synthesis of 133 studies from 1,480 records (§3.2–3.5). The surveyed methods were not rerun under a common benchmark.

## Claims and evidence

The survey organizes batching, prefill/decode disaggregation, tiered KV caches, GPU sharing, cold starts, checkpointing, and TEEs around throughput, latency, cost, and confidentiality. The corpus count is author-reported, not this note's reconstruction.

## Limitations and threats to validity

§3.2/§3.3 require peer review and exclude non-peer-reviewed preprints, whereas §7.3.1 says widely adopted, verified non-peer-reviewed systems were included in eligibility. §3.4 distinguishes the core corpus from contextual citations, but the two eligibility descriptions remain unreconciled. Search reproduction and a corpus audit are needed. The authors also note the gap between academic clusters and large commercial deployments.

## Comparison with related work

[NVIDIA's memory codesign](2026-nvidia-memory-full-stack-codesign.md) describes a vendor stack; [RIVET](2026-rivet-multiturn-llm-routing.md) evaluates model routing. Use this broader taxonomy to identify topics, then return to those specific conditions.

## Free-to-run verification plan and usage status

Proposed, not performed: choose three systems and tabulate their models, GPUs, workloads, TTFT, inter-token latency, and costs from primary papers. Avoid rankings across unmatched conditions. Usage status: proposed.

## Open questions and next checks

Audit the included-study list and search protocol, treatment of non-peer-reviewed sources, and primary measurements of selected systems.

## Primary sources

- [Supplied URL](https://arxiv.org/abs/2610.33475)
- [Primary HTML version examined](https://arxiv.org/html/2610.33475v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
