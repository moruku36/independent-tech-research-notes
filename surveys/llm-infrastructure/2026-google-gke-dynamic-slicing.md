**English** | [日本語](2026-google-gke-dynamic-slicing.ja.md)

# GKE dynamic slicing: resource topology and recovery

## Overview

- **What it is**: A GKE feature separates TPU provisioning from slice allocation.
- **What it says**: Super-slicing joins units; sub-slicing partitions them.
- **Caveat**: Hardware, GKE and reservation requirements limit applicability.

## Practical reading (six lines)

- Static nodepool topology restricts workload placement.
- Dynamic allocation reuses pre-provisioned capacity.
- The article reports faster startup and recovery.
- Our proposal: measure queueing and useful completion separately.
- Free check: map allocation/failure transitions on paper.
- It is not a generic GPU or home-server feature.

## Bibliography and verification scope

Kavitha Gowda and Wenzhe Li, Google Cloud, 2026-11-09; product engineering article.

Checked 2026-11-10 JST. Primary blog text returned by search and current official concept documentation checked; no cluster execution. Direct blog open failed.
Status: primary source checked / partially read / not reproduced.

## Question, method, claims and evidence

The blog's up-to-5× startup and 4.5× recovery claims are not universal results. The concept guide specifies Ironwood/TPU7x, Standard/Rapid and version-dependent super/sub-slicing requirements, with All Capacity restrictions; follow that guide rather than broad regional wording.

## Comparison with related work

Pathways provides execution coordination, while slicing supplies the topology beneath it. [Related note](2026-google-cloud-pathways-ga.md)

## Free check plan, usage status and next checks

Compare topology formation, fault isolation and application checkpoint recovery as different steps. Free check: create a requirements matrix from the concept guide; no reservation, cluster or paid run. Proposed only. Next: confirm target region, capacity mode and actual workload baseline before benchmarking.

## Primary sources

- [Requested source](https://cloud.google.com/blog/products/containers-kubernetes/gke-dynamic-slicing-on-tpus?hl=en)
- [Canonical article URL](https://cloud.google.com/blog/products/containers-kubernetes/gke-dynamic-slicing-on-tpus)
- [Supplementary official specification](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/dynamic-slicing)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
