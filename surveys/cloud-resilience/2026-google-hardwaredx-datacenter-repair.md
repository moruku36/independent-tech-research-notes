**English** | [日本語](2026-google-hardwaredx-datacenter-repair.ja.md)

# HardwareDx: graph-based diagnosis and repair time in datacenters

## Overview

- **What it is**: Google’s graph-based hardware diagnosis system for datacenter repair operations.
- **What it says**: In a production A/B comparison against deployed rules, the authors report mean repair-time reductions of 18.3% for H100 and 16.1% for a TPU platform.
- **Caveat**: The metric covers the test, diagnosis, and repair loop before return to service. Installation time is excluded.

## Practical reading (six lines)

- HardwareDx represents each machine’s components and connections, linking telemetry and logs to the relevant parts.
- A shared graph model learns from prior repair histories and can be adapted for other hardware platforms.
- Google randomized by machine against its existing diagnostic rules. The analysis used 225 H100 and 2,567 TPU repair windows.
- Mean repair time fell by 18.3% and 16.1%, respectively. Time at the repair percentile tied to the QA handover objective fell by 28.3% and 25.1%.
- A separate offline H200 evaluation reports less data needed after pretraining on H100. The evidence covers specific Google fleets and comparisons.
- Proposed use: document the start and end of repair, installation time, and the service-level threshold before evaluating a diagnostic change.

## Source and reading scope

*HardwareDx: A Foundational Graph Model System for Datacenter Machine Repairs*, Yuanlin Wen, Elan Markowitz, Zubo Gu, and colleagues. arXiv v1, November 17, 2026. The arXiv record states acceptance to NeurIPS 2026. Sections 3–4 and Appendix H were checked on November 22, 2026 JST. No deployment or independent reproduction was performed.

## Evidence and limitations

- **Design.** A graph per machine links replaceable parts, subcomponents, telemetry, symptoms and logs. The model maps different node types into a shared representation, then combines local message passing with global attention. Historical test-and-repair sequences and expert-labeled cases support component diagnosis and initial repair recommendations.
- **Production evidence.** Table 1 compares against the deployed, engineer-maintained rule system. HardwareDx handled 50% of H100 pilot machines and 20% of TPU machines. The mean time back to serving through testing, diagnosis and repair, excluding installation, fell by 18.3% ± 7.6% for H100 and 16.1% ± 2.6% for TPU. The QA measure is the time at the repair-case percentile needed to reach the contractual cluster handover service-level objective. Those reductions were 28.3% ± 10.7% and 25.1% ± 2.5%. The paper reports one standard error after each estimate. These are repair-window measures within the two fleets studied.
- **Transfer evidence.** In the offline H200 comparison, a model pretrained with H100 telemetry reached the authors’ production-grade performance with about one-tenth of the data needed by a model trained from scratch on H200. The historical rules comparison uses recommendations logged during repairs because historical rule versions cannot be fully replayed. Platform-specific data, labeling, and repair processes constrain extrapolation.

## Application and free check

Proposed. Use a synthetic fleet worksheet to record test start, diagnosis, repair completion, return to service, and installation. Calculate mean repair time and the percentile tied to a cluster readiness objective. Compare a rules-based triage baseline with topology-aware recommendations on the same cases before considering a live pilot.

## Related note

- [OpenAI Performance Factory’s regression investigation workflow](2026-openai-performance-factory-regression-workflow.md) provides a separate example of operational verification.

## Sources

- [arXiv record](https://arxiv.org/abs/2611.23398)
- [Inspected v1 text](https://arxiv.org/html/2611.23398v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
