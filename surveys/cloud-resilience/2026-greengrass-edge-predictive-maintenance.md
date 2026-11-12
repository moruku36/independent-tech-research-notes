**English** | [日本語](2026-greengrass-edge-predictive-maintenance.ja.md)

# Greengrass inference for predictive maintenance

## Overview

- **What it is** AWS IoT Greengrass v2 architecture for local predictive-maintenance inference and selective synchronization.
- **What it says** It reports 86.8% lower cloud-bound bytes in a 200-reading window and anomaly-class F1 of 0.84.
- **Caveat** The gateway is an EC2 t3.small and the data are simulated. Cloud-disconnection measurements remain planned.

## Practical reading (six lines)

- The hybrid configuration makes decisions locally and batches cloud-bound information.
- The comparison runs on AWS infrastructure.
- The printed 63.6 KB and 7.2 KB imply about 88.7% reduction, while the paper reports 86.8%.
- The 256× latency ratio compares MQTT PUBACK round trip with local ONNX inference.
- That boundary matters when estimating full application latency.
- A proposed study measures equivalent decision paths and separately tests disconnection.

## Source and reading scope

Prince Kwabena Appiah Boadu, Jeffery Baafi Kyei, Enoch Kofi Koranteng and Griffth Selorm Klogo. arXiv:2610.14815v1, 2026-10-10. Checked 2026-11-13 JST, selected PDF §§IV–VII and Tables III–VI. Conference acceptance is reported in arXiv metadata.

## Method, evidence and limitations

The measured means are 23.1 ms for cloud PUBACK and 0.09 ms for local inference. The CMAPSS-calibrated synthetic data and short measurement window limit generalization. The paper explicitly leaves quantitative disconnected-operation results for later work. From Table VI's printed volumes, (1 − 7.2/63.6) × 100 ≈ 88.7%, which differs from the reported 86.8%; the discrepancy is unresolved.

## Related notes

- [Manufacturing ML pipelines](2026-manufacturing-ml-event-pipeline.md)
- [AWS Emulator](2026-aws-emulator-local-testing.md)

## Free check and usage status

Proposed, untried. Define the same decision endpoint for local and remote paths. Use a fixed synthetic stream and record bytes, inference quality, latency and queuing separately. Next inspect measurement variability and repeat under actual disconnection before assessing resilience.

## Primary sources

- [Versioned record](https://arxiv.org/abs/2610.14815v1)
- [Inspected full text](https://arxiv.org/pdf/2610.14815v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
