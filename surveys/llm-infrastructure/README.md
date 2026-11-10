**English** | [日本語](README.ja.md)

# LLM serving infrastructure and cost-efficiency

Hardware choices, scheduling, KV cache control, and long-term memory retrieval.


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
