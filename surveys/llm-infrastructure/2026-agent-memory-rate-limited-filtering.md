**English** | [日本語](2026-agent-memory-rate-limited-filtering.ja.md)

# Agent memory: maintaining state instead of rereading history

## Overview

- **What it is**: A synthetic benchmark of current permissions after changing events.
- **What it says**: A model parses events and deterministic rules maintain state; benefits over full logs depend on reader and history length.
- **Caveat**: Known policy and synthetic domains limit generalization; dependency-aware retrieval can match filtering.

## Source and reading scope

- Tianhao Guo and Chongyao Guo, *Agent Memory as Rate-Limited Filtering: Explicit State Outlasts Long Context Beyond a Reader-Dependent Horizon*, arXiv:2611.02361v1, submitted November 2, 2026. [Full text](https://arxiv.org/html/2611.02361v1).
- Source URL: [Article / paper](https://arxiv.org/abs/2611.02361).
- Primary methods, comparisons, theory scope and replication/robustness passages checked November 16, 2026; not all proofs or artifacts audited; not reproduced.

## Practical reading

- The question is how to recover current permissions from a changing history.
- The filter separates model event parsing from deterministic state updates.
- It outlasts full logs under tested conditions, with a reader-dependent horizon.
- Proposed use: keep task status and approval changes as replayable structured events.
- Version transition rules and compare state against raw history and dependency-aware retrieval.
- The synthetic known-policy result is not a universal advantage over retrieval.

## Method, evidence and limitations

Paired histories change a deciding event's order or field; executable replay supplies answers. Model parsing plus explicit updates reaches 80–89% at 256 events. That is distinct from oracle-state results. The order-ignorant retention bound is not an impossibility theorem for all ordered-log readers.

## Related reading and comparison

A current-state record and a broader memory-consolidation design answer different design questions. These links are reading connections, not matched performance comparisons.

[Anthropic memory components](2026-anthropic-agent-memory-components.md) · [OpenClaw dreaming](2026-openclaw-dreaming-memory-consolidation.md)

## Free-to-run check

Free local check, proposed and unrun: write synthetic grant/revoke/expiry events and a deterministic reference reducer. Replay reordered pairs, duplicate events and restart checkpoints; check state and decision equality. Add an intentionally ambiguous event that must remain unresolved. This validates specified transitions without an LLM; it does not reproduce reader-accuracy results.

- **Usage status**: Proposed / untrialed / not adopted. No implementation, reproduction or external-environment validation was performed.

## Unconfirmed points and next checks

Next: test extraction errors, concurrent updates and schema changes on a realistic task. A memory's claim that permission exists must not itself become an authorization source.

- Category index: [Index](README.md)
