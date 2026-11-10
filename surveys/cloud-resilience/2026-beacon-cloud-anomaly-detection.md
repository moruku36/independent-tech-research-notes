**English** | [日本語](2026-beacon-cloud-anomaly-detection.ja.md)

# BEACON and asynchronous cloud anomaly detection

## Overview

- **What it is** Cloud observability paper about detecting anomalies with metrics, logs and service dependency graphs.
- **What it says** BEACON aligns metrics with logs and models delayed relationships across instances. It reports the highest segment-level F1 among the compared methods on three datasets.
- **Caveat** Segment-level hits can conceal late detection. The scores depend on dataset and scoring protocol.

## Practical reading (six lines)

- The paper asks how to combine different monitoring signals when dependent services react at different times.
- DIMA selects informative metric features and aligns metrics and logs in a shared prototype space.
- ASTP uses multiple time scales and service topology to incorporate observations from related instances.
- Table II reports segment F1 of 0.6688, 0.6292 and 0.8723 on AIOps2021, Train-Ticket and D1 respectively.
- An SRE trial could compare a metric-only rule with combined signals on a synthetic timeline with known delays.
- One hit within an anomalous interval is enough to score detection under the paper’s protocol. Record time to first alert separately.

## Bibliography and reading scope

Zhe Li, Tengxue Zhang, Yang Shu, Tung Kieu, Lunting Fan, Yingying Zhang and Bin Yang. arXiv:2610.27542v1, 2026-10-20. The arXiv record lists acceptance to ICDE 2027. Partially read on 2026-11-11 JST, covering §§III–IV and Table II.

## Method, evidence and limitations

The detector combines a prototype-based fusion module with topology-aware temporal aggregation. The study compares baselines and ablates model components across three datasets, including D1 from an anonymized production environment. The paper counts an anomalous segment as detected if any point is flagged and counts false alarms by normal segment. The reported F1 values therefore leave time to first alert and alert volume per hour unmeasured. Root-cause attribution needs separate evidence. Table II gives ContraAD an AIOps2021 F1 of 0.6138, while §IV-B1 gives 0.6271. This note uses the table for numeric comparisons.

## Related work

Incident-Arena studies SRE recovery and durable resolution. BEACON studies the earlier detection stage using observation data. Each stage needs evaluation suited to its operational role.

- [Incident-Arena](2026-incident-arena-sre-reliability.md)
- [Adaptive ephemeral chaos infrastructure](2026-adaptive-ephemeral-chaos-infrastructure.md)

## Free check and usage status

Proposed, untried. Create a two-service synthetic timeline with known onset, delayed downstream symptoms and normal intervals. Compare metric-only and combined-signal rules, holding the scoring intervals fixed. Record segment F1, time to first alert and false alerts per hour. Next verify dataset access, threshold selection and sensitivity to missing logs and topology drift. Model training and benchmark reproduction have yet to be performed.

## Primary sources

- [arXiv record](https://arxiv.org/abs/2610.27542v1)
- [HTML full text](https://arxiv.org/html/2610.27542v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
