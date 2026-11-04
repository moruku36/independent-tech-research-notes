**English** | [日本語](2026-quantum-safe-mechanisms-survey.ja.md)

# Quantum-safe cryptographic building blocks and migration

## Overview
- **What it is:** A survey of post-quantum and quantum cryptographic building blocks, applications and migration challenges.
- **What it says:** Integration across communications, IoT and other domains requires performance, compatibility and operational planning.
- **Caveat:** The literature includes proposals and prototypes; it does not uniformly establish production maturity or security.

## Source and scope
Ricardo Parizotto, Preeti Yadav, Marcus Freire, Anderson Tomkelski, Maycon Peixoto, Emmanuel Zambrini Cruzeiro and Israat Haque, [A Survey on Quantum-Safe Cryptographic Mechanisms: Building Blocks and Applications](https://arxiv.org/html/2609.11991v1), arXiv:2609.11991v1, submitted 9 September 2026. The supplied subtitle differs from the official title. Selected primary HTML abstract, search methods, taxonomy and main challenges checked 4 November 2026 JST. Individual cited studies, current standards, implementations and PDF not independently checked; no reproduction.

## Question and method
Future quantum computing could threaten some widely deployed public-key algorithms. The authors searched IEEE Xplore, Scopus and ACM Digital Library for work from 2020–2026, supplemented with exploratory references, and categorized building blocks and integration into applications. PQC algorithms run on conventional computers; quantum key distribution uses quantum communication and is a distinct mechanism.

## Findings and practical implications
The survey maps integration across communications, IoT, blockchains and other domains, discussing key and signature sizes, performance, interoperability and deployment. An application described in literature can be a prototype, not necessarily broad production deployment. Coverage depends on databases, query and selection criteria.

Inventory certificates, TLS, VPNs, signatures and libraries; assess protection lifetimes and upgrade paths. Check current provider and device documentation and test interoperability and performance before migration decisions. Do not choose algorithms or deploy QKD on this survey alone. Proposed usage only; no independent validation or reproduction.

[Security governance index](README.md)
