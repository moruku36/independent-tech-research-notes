**English** | [日本語](2026-workflowarena-executable-orchestration.ja.md)

# WorkflowArena: evaluating how agents organize executable work

## Overview

- **What it is**: A benchmark of agent-authored workflows across 145 tasks in eight domains.
- **What it says**: Fixed-executor transfers show that workflow authorship can change outcomes.
- **Caveat**: Model and harness are confounded; transferred instructions can convey task knowledge as well as structure.

## Practical reading (7 lines)

- The question is how decomposition, delegation and integration affect the delivered result.
- Each task shares a four-hour wall-clock limit among its agents; a 32-task transfer study fixes executors.
- The best overall resolved rate is 36.95%, averaged equally across domains.
- Opus-authored static workflows add 6.41 continuous-score points on average across four executors in that subset.
- Proposed use: specify dependencies, worker inputs, output contracts and integration checks before comparing workflows.
- Record coordination time and all workers' costs; worker count alone is not a quality metric.
- Single runs and unvalidated LLM grading limit certainty; no local reproduction was performed.

## Source and reading scope

Zheng Jiang et al., *WorkflowArena: Benchmarking Executable Workflow Orchestration in LLM-Based Multi-Agent Systems*, arXiv:2611.12856v1, November 9, 2026. [DOI](https://doi.org/10.48550/arXiv.2611.12856). Preprint; venue not independently confirmed.

Checked November 16, 2026. Primary HTML §§3–5 and Tables 1–2 checked; appendices and project artifacts not exhaustively audited. Primary source checked / not reproduced.

- [Requested full text](https://arxiv.org/html/2611.12856v1)
- [Abstract and submission history](https://arxiv.org/abs/2611.12856v1)

## Method, evidence and limitations

Nine models and 25 configurations use a recorded Workflow interface with native sub-agents disabled. Workflow sources cannot edit artifacts in the transfer experiment. Partial scores differ from full acceptance. Content/3D grading uses an LLM judge without measured human agreement. Each task/configuration runs once; transfers use only two authors and the selected subset (§5).

## Related reading and comparison

[Scaling agent systems](2025-scaling-agent-systems.md) asks when collaboration helps; [Conductor](2025-conductor-natural-language-orchestration.md) studies learning coordination. This benchmark adds a way to inspect agent-authored execution and integration. These are related questions, not matched leaderboard results.

## Free-to-run check and usage status

Proposed, free and unrun: make a tiny offline task with two dependent files and a deterministic final checker. Hand-author sequential, parallel-independent and missing-integration traces. Confirm that valid components without a consistent final artifact fail acceptance; record handoffs, coordination time and completion separately. This tests the local verifier and reporting schema, not the paper's model results. Later model comparisons should hold task, executor, tools and total budget fixed and repeat trials.

Proposed / untrialed / not adopted. No agent workers, benchmark jobs or paid API calls were launched.

## Unconfirmed points and next checks

Next: inspect verifier coverage, task selection, pinned harness versions and resource accounting before reproducing. Preserve unresolved outcomes and regressions. Do not treat this custom Workflow setup as evidence for default Codex behavior or a universal benefit from adding agents.

[Category index](README.md) | [Reading list](../../docs/reading-list.md)
