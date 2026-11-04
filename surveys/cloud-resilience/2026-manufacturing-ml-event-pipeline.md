# Event-Driven Machine Learning Infrastructure for Manufacturing

[日本語](2026-manufacturing-ml-event-pipeline.ja.md) | [Theme index](README.md)

- **Source:** [arXiv:2610.06890v1](https://arxiv.org/html/2610.06890v1), industry report accepted at IC2E 2026, submitted 24 September 2026.
- **Authors:** Zhengyang “Cissy” Gu, Thomas Cook, Fredaljohn Rohrbaugh, Joseph E. Hernandez, Chris Couch.
- **Scope:** Main text, cost table and simulation reviewed; no independent cost audit or reproduction.

## Summary
Liveline Technologies reports an AWS event-driven GPU training pipeline for manufacturing, combining an operational cost account with a separate discrete-event simulation of orchestration failure handling. The authors are affiliated with the company and the work is funded by it.

## Method and findings
The report describes more than 40,000 training jobs across three years and multiple plants. Its design uses SQS and dead-letter queues, Lambda admission control with concurrency two, reusable ECS/EC2 GPU workers, Conductor on Fargate, and Terraform. The authors report per-facility monthly costs of $3,200 for an always-on baseline, $910 for on-demand only, and $760 for a Spot/checkpoint-enabled LPP design: approximately 72% and 76% lower, respectively, under their assumptions.

Separately, a 52-week simulation of 2,077 jobs on two GPUs reports 1,342 lost jobs for naive retry exhaustion without a dead-letter queue; Step Functions and the proposed design had no simulated losses. These are simulated results, not observed production losses.

## Practical interpretation
For an AWS lab, consider queue-based admission, warm worker reuse, dead-letter handling and checkpointing; measure queue age, GPU utilization, completion and total costs under actual workloads. Treat GCP/Azure implementations as designs requiring separate validation.

## Limits
This is one company's self-reported experience and a modeled workload. Simulation omits network jitter, throttling and availability-zone outages. Cost, resilience and portability cannot be generalized without local measurement.
