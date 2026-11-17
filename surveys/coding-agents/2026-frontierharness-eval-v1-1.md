**English** | [日本語](2026-frontierharness-eval-v1-1.ja.md)

# FrontierHarness v1.1: model–harness fit and cost measurement

## Overview

- **What it is**: RUNTA/Baseten's vendor evaluation of terminal-agent harness configurations.
- **What it says**: Cost and success rankings depend on the model–harness pair.
- **Caveat**: One provider's open-model results do not rank the user's current closed-model workflow.

## Practical reading (six lines)

- The question is whether changing models should prompt a fresh harness comparison.
- The study crosses 22 configurations, five models, 62 tasks, and four attempts.
- Reported cost ranks move substantially between models.
- Proposed use: compare a few pinned model–harness pairs on one's own tasks.
- Record pass rate, cost per task, cost per pass, timeouts, and invalid passes separately.
- Small pass-rate gaps and observational trace patterns do not prove a universal winner.

## Source and reading scope

Shilin Zhu, “Introducing FrontierHarness Eval v1.1,” RUNTA, 2026-11-17. Checked 2026-11-18 JST in browser: methodology table, figures, limitations, and selected appendix configuration/trace tables. Harbor trials use fresh RUNTA runtimes; harness versions/settings stay fixed across Baseten-served models at maximum reasoning effort. Vendor evaluation partially read; underlying trial logs/jobs not downloaded or rerun.

## Evidence and limitations

There are 18 harnesses but 22 configurations. Codex CLI's per-task cost rank changes from first with GLM-5.3 to 16th with Kimi-K3; this differs from cost-per-pass ranking. A pass is a scored trial, not pass@4. Reward-hacked trials fail, infrastructure errors are rerun, and unpriced trials are excluded from cost estimates. The article reports task-bootstrap uncertainty around ±10 percentage points for a model/harness cell.

Costs use Baseten token list prices, not subscription charges or full engineering/runtime cost. The best-value card uses a stated trade-off rule, not simply maximum pass rate. Sparse subagent use and cache patterns are observations, not causal ablations.

## Application and free check

Proposed / untried. First make a free offline ledger of existing completed and failed tasks, acceptance tests, model IDs, harness versions, environment restrictions, and known price omissions. Before later paid runs, freeze task inputs and scorer, randomize order, budget retries, and audit traces for verifier access or solution lookup. Compare paired task outcomes with uncertainty and a minimum useful improvement. Do not infer that the published Codex CLI result measures ChatGPT/Codex with GPT models.

Usage status: proposed / untried / not adopted. No model calls, environment changes, or experiments were performed for this note.

## Related notes

- [Architecture cost study](../llm-infrastructure/2026-enterprise-sop-agent-architecture-cost.md)
- [Verification practice](2026-claude-code-verification-practices.md)

These are reading comparisons, not matched performance evaluations.

## Sources

- [Supplied evaluation / 指定の評価報告](https://runta.com/blog/introducing-frontierharness-eval-v1-1/)
- [Linked dashboard / 記事のダッシュボード](https://frontierharness.org/)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
