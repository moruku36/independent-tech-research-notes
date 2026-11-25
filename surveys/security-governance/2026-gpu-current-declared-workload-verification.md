**English** | [日本語](2026-gpu-current-declared-workload-verification.ja.md)

# GPU supply current for verifying declared AI workloads

## Overview

- A preprint on checking declared AI workloads with GPU supply-current measurements.
- A detector fitted on permitted activity flagged the studied deviations on one NVIDIA H200 NVL.
- The result depends on a trustworthy, representative baseline. An alert warrants investigation and does not identify the workload by itself.

## Six practical takeaways

- The study records 23.4 hours of electrical current from one H200 NVL under varied conditions.
- The detector learns the reference signature of declared idle and inference workloads.
- With the complete reference, at least 99.9% of windows in the tested prohibited-work groups were flagged.
- The continuous evaluation detected 188 of 188 staged episodes with a median delay of 3 seconds and one alarm in 8.8 hours of declared work.
- Omitted or unreliable reference data can undermine the monitor. One GPU and one 168M-parameter model bound the evidence.
- Proposed use. Treat alerts as audit leads and track baseline coverage, independent checks and false alarms.

## Publication and review scope

Tom Kimpson, arXiv:2611.29982v1, submitted November 23, 2026. Reviewed the abstract, results and discussion on November 26, 2026 JST. No reproduction.

## Evidence and limitations

- The sensor measures electrical current on the auxiliary supply. The paper uses a one-class model to score departures from the reference activity.
- The window-based detection rates and episode-level detection rates answer different questions. Generalizing to varied inference workloads or multi-node clusters requires new evidence.
- Reference completeness and integrity affect both missed detections and false alarms. A deviation indicates a mismatch with the reference and can arise from legitimate changes.

## Application and low-cost check

Proposed and untried. Prepare a paper audit plan covering the declared workloads, authority to collect reference data, benign holdout workloads, and how to review an alarm. Log legitimate workload changes before comparing observations.

## Related notes

- [Managing frontier-model risk](../agent-safety/2026-openai-frontier-risk-model-lifecycle.md)
- [Shirudo and measured host state](2026-openai-cisco-shirudo.md)

## Sources

- [arXiv v1 abstract](https://arxiv.org/abs/2611.29982v1)
- [Full preprint](https://arxiv.org/html/2611.29982v1)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
