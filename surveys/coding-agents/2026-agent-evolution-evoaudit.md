**English** | [日本語](2026-agent-evolution-evoaudit.ja.md)

# Agent evolution: preserving earlier successes with EvoAudit

## Overview

- **What it is**: An audit of fixed-weight agent harness evolution.
- **What it says**: All 16 evaluated evolved agents gain tasks and lose earlier coverage; EvoAudit guides revised evolution operators.
- **Caveat**: Single-model, selected-benchmark evidence does not establish universal improvement or failure.

## Source and reading scope

- Xiaobo Wang et al., *Beneath the Surface: What We Overlook When We Talk About Agent Evolution*, arXiv:2611.07624v1, submitted November 5, 2026. [Full text](https://arxiv.org/html/2611.07624v1).
- Source URL: [Article / paper](https://arxiv.org/abs/2611.07624).
- Primary setup, repeated-evaluation metrics, results, EvoAudit/AGE and limitations checked November 16, 2026. All trajectories and code were not audited; not reproduced.

## Practical reading

- The question is what an improved average hides during harness evolution.
- Repeated trials separate reliable success from at-least-once coverage.
- All sixteen evolved agents gain tasks while losing earlier coverage.
- Proposed use: preserve a baseline and report gains, regressions, cost and latency together.
- Use held-out work and a fallback revision before promoting an evolved skill.
- Single-model evidence limits generalization; EvoAudit offers revisions, not a guarantee.

## Method, evidence and limitations

Four methods × two harnesses × two benchmarks use GPT-5.4. Avg@8 measures mean success; Pass@8 measures success at least once in eight trials. Coverage is not an inherent capability bound. Transfer varies by task. EvoAudit revises selection, analysis, mutation and gating; one lineage per condition limits certainty.

## Related reading and comparison

Use this audit lens when reading self-improvement methods: ask which old successes survive, not only how new ones are discovered. No cross-paper ranking is inferred.

[Failure-trace lessons](2026-frozen-weight-failure-trace-lessons.md) · [Darwin Gödel Machine](2025-sakana-darwin-godel-machine.md)

## Free-to-run check

Free local check, proposed and unrun: replay an existing, non-sensitive result fixture through a comparison script. Include newly passing, regressed and unchanged tasks, repeated-run outcomes and recorded costs. Verify that a higher mean cannot hide regressions in the report. This checks reporting logic; fresh model experiments require a separate execution budget.

- **Usage status**: Proposed / untrialed / not adopted. No implementation, reproduction or external-environment validation was performed.

## Unconfirmed points and next checks

Next: freeze the model/version, data splits, evaluator and cost boundary before a real comparison. Promotion thresholds should be task-specific, not borrowed as universal constants from this paper.

- Category index: [Index](README.md)
