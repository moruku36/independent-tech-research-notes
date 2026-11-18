**English** | [日本語](2026-aws-well-architected-foundations-workloads.ja.md)

# AWS Well-Architected 2026: cloud foundations and workloads

## Overview

- **What it is** AWS's update to its cloud architecture guidance.
- **What it says** It distributes shared controls and per-workload decisions across Foundations and Workloads.
- **Caveat** The counts describe guidance items. Operational impact was not measured here.

## Practical reading (six lines)

- Evaluate account-wide controls once for workloads that inherit them.
- Foundations contains 45 practices in seven capabilities.
- The workload guidance moved from 307 to 216 practices after relocation, consolidation and retirement.
- The six pillars include revised guidance for secure coding and backup resilience.
- Assign owners and evidence to shared controls and workload-specific checks.
- Keep human judgment in the review where configuration and telemetry cannot answer the question.

## Source and reading scope

AWS Architecture Blog, November 16, 2026. Checked AWS's November 18 Japanese translation and the framework release notes on November 19, 2026 JST. The supplied Japanese path did not load through web retrieval.

## Evidence and limitations

The release notes confirm that the six pillar whitepapers were consolidated. Of the 45 foundation practices, 33 came from existing pillars by relocation or consolidation. AWS describes the remaining coverage as adequate for its technical scope. The announcement does not supply measured review-time savings.

## Application and free check

Proposed and untried. Map one existing workload's checklist to shared identity, logging, and cost controls, then note the workload-specific evidence for backup recoverability.

Usage status is proposed. This reading note did not include deployment or independent reproduction.

## Sources

- [AWS official Japanese translation](https://aws.amazon.com/jp/blogs/news/announcing-updates-to-the-aws-well-architected-framework-3/)
- [AWS release notes](https://docs.aws.amazon.com/wellarchitected/latest/framework/release-notes.html)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
