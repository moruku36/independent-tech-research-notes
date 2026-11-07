**English** | [日本語](2026-cvm-store-confidential-vm-storage.ja.md)

# CVM-Store: A Secure Storage System for Confidential Virtual Machines

## Overview

- Systems preprint extending confidentiality, integrity, and freshness to storage outside a confidential VM.
- It overlaps userspace NVMe I/O with authenticated encryption and uses external trusted counters to detect stale states.
- Performance depends on size and synchronization; unsynchronized loss, visible metadata, and external trust remain.

## Practical reading (7 lines)

- Protecting CVM memory does not by itself encrypt persistent data or prevent rollback.
- CVM-Store overlaps userspace I/O and cryptography and offers KVS, log, and file APIs.
- An external trusted counter tracks committed epochs and detects stale storage state.
- Large-object bandwidth approaches raw NVMe, but some measurements synchronize only at shutdown.
- Proposed application: specify object sizes, access patterns, sync frequency, and tolerable crash loss first.
- Unsynchronized writes may be lost; freshness and durability of every write are separate guarantees.
- Applications adopt its APIs; metadata confidentiality and DoS prevention are not provided.

## Source and verification scope

- Original title: CVM-Store: A Secure Storage System for Confidential Virtual Machines.
- Authors: Thore Sommer, Masanori Misono, Dimitrios Stavrakakis, Pramod Bhatotia.
- arXiv:2610.34560v1, 2026-10-25. The arXiv comments report NDSS'27 acceptance; venue-side confirmation not checked.
- Checked 2026-11-08 JST: primary HTML APIs/threat model (IV), design (V–VI), security (VII), implementation (VIII), evaluation (IX), and relevant Appendices A–B, partially. No implementation execution or hardware reproduction. Status: partially read.

## Research question

Can a CVM protect persistent data from an untrusted host/storage stack while retaining high NVMe throughput?

## Method, data, and comparison conditions

A CVM-hardened SPDK engine pipelines authenticated encryption and I/O. Access-aware KVS, append-log, and write-once file abstractions combine with epoch-batched external counters. Evaluation uses two AMD SEV-SNP servers and KIOXIA CM7-R NVMe against ext4 and Rollbaccine. Applications integrate the library APIs rather than retaining POSIX unchanged (IV, IX).

## Claims and evidence

Large objects reportedly come within about 1% of raw NVMe write bandwidth and 1–19% of read bandwidth. IX-B uses non-blocking execution with shutdown-only synchronization. IX-C synchronizes per fsync/barrier and reports strong checkpoint/log results, while small-operation workloads can trail; Filebench-style mail reaches 0.29× ext4. Freshness overhead additionally depends on epoch length and external round-trip latency.

## Limitations and threats to validity

Trusted components include confidential-computing hardware, guest software, attestation, and external counter services. File sizes and access patterns remain visible; DoS, side channels, and physical attacks are out of scope. Unsynchronized operations may be lost after adversarial restart. Files are write-once, and live migration is unsupported. Results do not generalize to arbitrary clouds, small objects, or strict per-operation sync.

## Comparison with related work

The [cloud LLM survey](../llm-infrastructure/2026-llms-cloud-architecture-orchestration-survey.md) introduces confidential computing; this paper details persistent I/O and recovery freshness. [Kubernetes agent containment](2026-kubernetes-autonomous-agent-containment.md) controls operations, whereas this paper protects stored state. It does not replace authorization or application correctness.

## Free-to-run verification plan and usage status

Proposed, not performed: create a requirements matrix separating confidentiality, tamper detection, freshness, durability, and availability for a fictional workload. Trace a crash after the last synchronization point on paper. No specialized hardware or paid cloud experiments. Usage status: proposed.

## Open questions and next checks

Check artifact versions, synchronization completion semantics, crash boundaries, external-counter recovery/trust, and performance under matched durability.

## Primary sources

- [arXiv:2610.34560](https://arxiv.org/abs/2610.34560)
- [Primary HTML examined v1](https://arxiv.org/html/2610.34560v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
