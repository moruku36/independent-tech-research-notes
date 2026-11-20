**English** | [日本語](README.ja.md)

# LLM serving infrastructure and cost-efficiency

Hardware choices, scheduling, KV cache control, and long-term memory retrieval.


## Added 2026-11-20

- [Attention Is All You Need: the original Transformer](2017-attention-is-all-you-need.md) — NeurIPS 2017. Attention architecture, training conditions, and English–French BLEU discrepancy.

## Added 2026-11-19

- [Azure Cobalt 200 VMs: workload performance and availability](2026-azure-cobalt-200-vm-workload-performance.md) — Official launch announcement. Regional availability and vendor workload comparisons.
- [Nemotron-Labs-Sigma: continuous diffusion and decoding throughput](2026-nemotron-labs-sigma-continuous-diffusion.md) — Preprint v2. Few-step distillation, measured GB200 throughput, and comparison limits checked.

## Added 2026-11-18

- [Enterprise SOP agents: cost–success trade-offs and inconsistent reporting](2026-enterprise-sop-agent-architecture-cost.md) — Preprint v1. Mock-tool comparisons and body/conclusion/scoring inconsistencies recorded.

## Added 2026-11-17

- [QD-Rec: evolving diverse reasons for recommendations](2026-sakana-qd-rec-open-ended-recommendation.md) — Preprint v2 and official technical article. Recommendation archives, judge reuse, non-uniform gains, and code/model differences checked.

## Added 2026-11-16

- [WorkflowArena: evaluating how agents organize executable work](2026-workflowarena-executable-orchestration.md) — Preprint v1. Integrated acceptance, macro-averaging, transfer controls and limitations checked.
- [Agent memory: maintaining state instead of rereading history](2026-agent-memory-rate-limited-filtering.md) — Preprint v1. Deterministic updates, reader-dependent horizon and synthetic scope checked.

## Added 2026-11-15

- [TRINITY: learned model and role selection](2025-trinity-evolved-coordinator.md) — Preprint v3. Role selection and evaluation scope checked.
- [Conductor: learning natural-language coordination](2025-conductor-natural-language-orchestration.md) — Preprint v5. Workflow representation and training checked.
- [Fugu: reviewing the product report against its foundations](2026-fugu-orchestration-report-review.md) — Secondary article. Primary architecture passages cross-checked.
- [Unsloth Qwen3.8: quantization and local serving](2026-unsloth-qwen38-local-inference.md) — Vendor guide. 27B scope and memory units checked.
- [GLM-5.3 across two DGX Stations: capacity and concurrency](2026-glm53-two-dgx-stations.md) — Vendor tutorial. Aggregate throughput and latency checked.

## Added 2026-11-13

- [Scaling agent systems through task–architecture alignment](2025-scaling-agent-systems.md) — Preprint v3. Coordination results and evaluation limits checked.
- [DLite and history-free speculative decoding](2026-dlite-history-free-speculation.md) — Preprint v1. Architecture and inference metrics checked.

## Added and rechecked 2026-11-12

- [EC2-Bench and edge–cloud agent collaboration](2026-ec2-bench-edge-cloud-agents.md) — Preprint v2. Task curation and exposure metric checked.
- [HARP preference inference — withdrawn preprint](2026-harp-preference-inference-withdrawn.md) — Withdrawn v2. Earlier v1 inspected as historical material.
- [RIVET routing — v2 rechecked](2026-rivet-multiturn-llm-routing.md) — Existing note rechecked, with no new paper entry.

## Added 2026-11-11

- [Shattered on self-hosted LLM and API costs](2026-shattered-self-hosted-llm-vs-api.md) — Editorial comparison with illustrative cost estimates.

## Added 2026-11-10

- [Cloud Pathways GA: a runtime for multi-slice ML](2026-google-cloud-pathways-ga.md) — Primary source partially checked; not reproduced.
- [GKE dynamic slicing: resource topology and recovery](2026-google-gke-dynamic-slicing.md) — Primary source partially checked; not reproduced.
- [TPU Sync: moving KV cache and model weights](2026-google-tpu-sync.md) — Primary source partially checked; not reproduced.
- [Nexus: persistent execution and authority across devices](2026-nexus-cloud-edge-execution.md) — Primary source partially checked; not reproduced.
- [Let Them Sleep: RSPM and the risk of excessive pruning](2026-rspm-self-pruning-memory.md) — Primary source partially checked; not reproduced.
- [Do agents need to sleep? A testable theory of consolidation](2026-do-agents-need-sleep.md) — Primary source partially checked; not reproduced.

## Added 2026-11-09

- [OpenClaw Dreaming: evidence-backed external-memory consolidation](2026-openclaw-dreaming-memory-consolidation.md) — Official product documentation; phases, provenance, and rewrite validation checked; code/runtime unverified.

## Added 2026-11-08

- [The components of agent memory](2026-anthropic-agent-memory-components.md) — Corporate technical article; external-memory, search, and wiki evidence checked; answering savings separated from preparation costs; not reproduced.

## Added 2026-11-07

- [Wider or Deeper? Scaling LLM Inference-Time Compute with Adaptive Branching Tree Search](2025-sakana-adaptive-branching-mcts.md) — Research article + paper v5; search partly checked; Pass@250 distinguished from final selection; not reproduced.

- [LLMs in Cloud: A Discussion on Architecture, Orchestration, and Inference](2026-llms-cloud-architecture-orchestration-survey.md) — Survey preprint; methods and discussion partly checked; selection inconsistency recorded; cited performance unverified.

## Added 2026-11-06

- [RIVET: accuracy and cost in multi-turn LLM routing](2026-rivet-multiturn-llm-routing.md) — Main primary-source sections checked; no reproduction or independent validation.
- [NVIDIA's memory hierarchy and full-stack codesign](2026-nvidia-memory-full-stack-codesign.md) — Main primary-source sections checked; no reproduction or independent validation.

- [Demystifying Cost-Efficiency in LLM Serving over Heterogeneous GPUs](2025-heterogeneous-gpu-llm-serving.md) ([arXiv:2502.00722](https://arxiv.org/abs/2502.00722), v2, 2025): benchmark of six GPU types and a MILP scheduler for GPU composition, deployment, and workload assignment under a price budget. Partially read (stops mid-§4.2); venue unconfirmed; no reproduction.

- [Cache Engineering for Agents](2026-cache-engineering-for-agents.md) ([arXiv:2610.28577v1](https://arxiv.org/html/2610.28577v1), 2026): direct agent KV control. Main sections and appendix partially read; code and reproduction unverified.

- [Raw-RAG versus agentic memory](2026-raw-rag-agentic-memory.md) ([arXiv:2610.30755v1](https://arxiv.org/html/2610.30755v1), 2026): raw-history retrieval versus complex memory management. Primary body and selected appendix material checked; partially read; code and reproduction unverified.

- [Google Sleep: continual learning and memory consolidation](2026-google-sleep-continual-learning.md) — Google blog and underlying preprint partially checked; not reproduced.

[Survey index](../README.md) | [Repository README](../../README.md)

- [Recursive Multi-Agent Systems](2026-recursive-multi-agent-systems.md) — article and paper counted as one study; primary v2 selected sections checked, no reproduction.
