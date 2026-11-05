**English** | [日本語](2026-kubernetes-autonomous-agent-containment.ja.md)

# Containing autonomous agents on Kubernetes through layered controls

## Overview

- Preprint proposing a threat model and reference architecture for AI agents operating Kubernetes.
- It proposes seven layers of controls, including tool authorization, identity, isolation, network, secrets, and runtime response.
- Evaluation is qualitative; it reports no measured attack success or overhead.

## Practical reading (7 lines)

- Logs and tickets read by an operations agent can contain instructions that redirect it.
- The paper requires infrastructure controls to hold even if the model follows such input.
- It maps identity, RBAC and admission, isolation, network, tool mediation, data, and runtime monitoring into seven layers.
- It provides EKS, AKS, and GKE bindings plus an approval-gated request walkthrough.
- A practical starting point is enforcing tool-argument policy and Kubernetes API policy independently.
- Test a small read-only setup against denied actions and egress before expanding privileges.
- The paper does not measure effectiveness, latency, or cost of the proposed stack.

## Source and verification scope

Simhadri Podala Narasimha, arXiv:2610.02861v1, 2026-10-02. Primary HTML abstract, architecture, evaluation, and limitations checked on 2026-11-06 JST. Partial reading; no reproduction.

## Method, claims, and evidence

The design study groups ten threat classes, nine principles, seven control layers, and governance, with mappings for EKS, AKS, and GKE. Evaluation consists of a threat–control matrix and four attack walkthroughs, followed by a proposed empirical method.

## Limitations and open questions

No measured attack-success, latency, or cost figures. The coverage matrix is the author's assessment, and no red-team test of the example artifacts is reported. Product and API versions may change.

## Comparison with related notes

Adds concrete infrastructure enforcement points to the repository's agent-safety and cloud-control notes.

## Low-cost verification plan and use status

Proposed, not performed: use a local Kubernetes cluster with a read-only agent and record whether unauthorized API calls and external egress are denied.

## Primary source

- [Specified primary source](https://arxiv.org/html/2610.02861v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
