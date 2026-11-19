**English** | [日本語](2026-guard-regret-guided-harness-improvement.ja.md)

# GUARD: regression-aware harness updates with frozen models

## Overview

- **What it is** A preprint on continual updates to an agent’s text harness around a frozen model.
- **What it says** GUARD uses task checklists to identify regressions and gate candidate edits.
- **Caveat** The formal guarantee concerns self-review on the gate’s evaluated tasks.

## Practical reading (six lines)

- Fix the task checklist before running the agent.
- Distinguish behavior broken by an edit from criteria that were already failing.
- Compare candidate edits on the same tasks and evaluate newly introduced regressions before promotion.
- After adaptation, use one frozen harness and a single run per test task.
- On 43 hosted calendar tasks, the final GUARD setup used 54.5% fewer tokens than the static baseline.
- For a small trial, score protected behavior and unseen tasks separately from the aggregate.

## Source and reading scope

Minghe Zhang et al., *GUARD: Stabilizing Recursive Self-Improvement with Regret Guidance*, arXiv:2611.23476v1, submitted November 17, 2026 UTC. Checked November 20, 2026 JST. Partially read §§2, 4–6 and the main result tables. Independent replication was not checked.

## Evidence and limitations

- **Adaptation and guarantees (§§2, 4).** Adaptation uses observable execution and model self-review, with the official evaluator reserved for testing. Soft-HURT allows some task-level drops under its limits. The aggregate guarantee covers the self-review objective on the gate buffer. Generalization to shifted tasks depends on additional evidence.
- **Hosted EvoHarnessBench (§6.2, Table 2).** With Gemini 4 on 43 calendar tasks, the final setup scored 80.80% ACC versus 71.91% for the static baseline. Mean test tokens fell from 131,032 to 59,651, while mean latency rose from 221.6 to 233.8 seconds. Adaptation costs are outside the inference comparison. Five GUARD configurations were evaluated on this same split. The comparison with Meta-Harness reported p = 0.11.
- **Promotion audit (§6.4, Table 4).** The 19 admitted execution-gated updates met or exceeded the initial harness on their active held-out cohorts, with 15 improvements and four ties. That comparison uses the initial harness and cohort scores, whereas the gate checks a candidate against the incumbent on adaptation tasks.

## Application and free check

Proposed and untried. Prepare a small local document-processing fixture and archived before/after results. Mark deliberate improvements, old gaps, and new failures, then compare aggregate scoring with per-criterion review. Keep separate acceptance cases and track adaptation effort apart from inference usage.

Usage status is proposed. No replication was performed.

## Related notes

- [Self-Improvement Memory](2026-self-improvement-memory-continual-rsi.md)
- [Self-organized improvement through gameplay](2026-self-organized-agent-improvement-gameplay.md)

## Sources

- [Primary report, arXiv v1](https://arxiv.org/html/2611.23476v1)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
