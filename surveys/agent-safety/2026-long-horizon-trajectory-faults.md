**English** | [日本語](2026-long-horizon-trajectory-faults.ja.md)

# Long-horizon failures: tracing origins, evidence and recovery

## Overview

- **What it is** Trajectory-based analysis of how agent errors begin, spread and survive recovery attempts.
- **What it says** In 68 of 95 failed runs, evidence contradicting the error appeared before failure.
- **Caveat** Failed-run sampling and LLM annotation limit generalization; proposed controls were not experimentally deployed.

## Practical reading (six lines)

- The record links fault origin, propagation, detection, response and consequence.
- It distinguishes execution phase from the affected state domain.
- Only seven of the 68 evidence-containing runs acted on that evidence.
- Retrying can retain the erroneous belief that caused the failure.
- A separate raw-log scan identifies harness-generated fallback answers after provider errors.
- Proposed application: log evidence consumption and verify that recovery actually changes corrupted state.

## Source and reading scope

Shaohuang Wang, Jinghao Wen, Xulei Zhang and Xun Jiao, *Dependable Long-Horizon LLM Agents: A Trajectory-Centered Empirical Study of Where Errors Enter and Which Controls Reach Them*. arXiv:2611.13254v1, 2026-11-09. Checked 2026-11-14 JST, selected §§2–5 and Tables 1–4. Venue unconfirmed.

## Method, evidence and limitations

One Claude instance annotates each trace under a written protocol. Human inter-annotator agreement is unavailable. The sample is batch-selected and excludes very long traces; it contains failures rather than a population success denominator. Claims that controls would reach a fault are retrospective judgments, not measured prevention rates.

## Related notes

- [Auditable belief updates](2026-eb-mas-auditable-beliefs.md)
- [Workflow structural testing](2026-agent-workflow-structural-testing.md)

## Free check and usage status

Proposed, untried. On a synthetic local task, preserve numbered observations, claims, state changes and recovery decisions. Add a known contradiction and compare retrying with explicitly correcting the saved belief. Check both final acceptance tests and whether the contradicted claim survives. No external effects are needed. Next audit a few annotations manually and distinguish model, tool and harness termination before measuring control effectiveness.

## Sources

- [Versioned record](https://arxiv.org/abs/2611.13254v1)
- [Inspected text](https://arxiv.org/html/2611.13254v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
