**English** | [日本語](2025-scaling-agent-systems.ja.md)

# Scaling agent systems through task–architecture alignment

## Overview

- **What it is** Empirical research on when multi-agent coordination helps.
- **What it says** Coordination improves financial analysis and degrades sequential planning under the evaluated conditions.
- **Caveat** Results are conditional on tested workloads, models and budgets.

## Practical reading (six lines)

- The study compares one agent with independent, centralized, decentralized and hybrid teams.
- It evaluates 260 configurations across six benchmarks and three model families.
- Reported relative changes range from +80.8% in financial analysis to −70.0% in planning.
- Coordination adds communication costs and can propagate mistakes.
- Proposed application: compare a single worker against task decomposition plus a reviewer in the current harness.
- Coding and terminal evaluations use only 20 instances each; reported thresholds need local validation.

## Source and reading scope

Yubin Kim et al., *Towards a Science of Scaling Agent Systems*. arXiv:2512.08296, first posted 2025-12-09; inspected v3 dated 2026-04-08. Checked 2026-11-13 JST. Partially read §§3–5, Tables 1–5 and data/code availability. Earlier versions were not compared; venue unconfirmed.

## Method, evidence and limitations

Tools and prompts are controlled, with total iteration budgets matched. Cross-validated R² is 0.373 (0.413 using ACI, mean single-agent performance). The 87% result concerns within-domain held-out architecture selection. Approximate 45% single-agent saturation is an empirical boundary. Six dataset clusters limit statistical inference; tool-overhead and error-amplification patterns need caution.

## Related notes

[RecursiveMAS](2026-recursive-multi-agent-systems.md) explores a different communication mechanism. [Swarm user report](../coding-agents/2026-antigravity-swarm-reddit-report.md) provides an individual experience, useful for generating hypotheses.

## Free check and usage status

Proposed, untried. Start with free offline inspection of the paper-linked artifacts and a ledger for task outcomes, tools, messages, reasoning tokens, elapsed time and reviewer effort. A later small local trial could fix model, prompts, tools and total budget across a single worker and delegated variants. Separate decomposable tasks from sequential tasks, repeat trials, and use fixed acceptance tests. Existing local inference would be needed for a no-API-cost run. Next verify code coverage of v3, budget accounting, selection validation and uncertainty before implementation.

## Primary sources

- [arXiv v3](https://arxiv.org/abs/2512.08296v3)
- [Inspected text](https://arxiv.org/html/2512.08296v3)
- [Paper-linked code, execution unverified](https://github.com/ybkim95/agent-scaling)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
