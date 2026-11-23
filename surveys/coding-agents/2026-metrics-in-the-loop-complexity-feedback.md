**English** | [日本語](2026-metrics-in-the-loop-complexity-feedback.ja.md)

# Metrics-in-the-Loop: complexity feedback during coding runs

## Overview

- **What it is**: A preprint on feeding automatic complexity and coverage measurements back to coding agents during execution.
- **What it says**: Complexity reports reduced the measured concentration of complexity on Commit0 and SlopCodeBench across all four models. SWE-EVO estimates were less conclusive per model.
- **Caveat**: The complexity metric can decrease after function extraction. Long-term maintenance and equivalence in correctness remain unestablished.

## Practical reading (six lines)

- After measurable code-changing turns, the harness can report complex functions and recently changed lines missed by tests.
- The five conditions distinguish no feedback, a reminder, complexity, coverage, and combined feedback.
- Complexity feedback reduced the share of weighted complexity in functions above the threshold of 10 in both main benchmark comparisons.
- The per-model intervals for held-out correctness in Table 1 include zero. They also allow meaningful losses in some cases.
- Inlining eligible single-use functions removed much of the measured gap in some settings, so total branching can tell a different story.
- Proposed use: sample matched tasks with reminders and complexity feedback, then check hidden tests, branching, review effort, and later edits.

## Source and reading scope

Nicolas Chapados, Jean-François Gagné and Nouha Dziri, *Metrics-in-the-Loop: Complexity Feedback Reshapes Agent-Written Code*, arXiv v1, November 18, 2026. Checked Sections 2–4, Table 1 and selected appendices on November 24, 2026 JST. No evaluation runs were reproduced.

## Evidence and limitations

- **Design and measurement.** Four models and one harness run three Python benchmarks. The reminder and measurement arms share feedback instructions. E10 weights each main-code function’s cyclomatic complexity by the square root of its nonblank, noncomment line count and reports the share contributed by functions above 10. The authors grade correctness separately on tests held outside the agent’s workspace.
- **Results.** Complexity-only and combined feedback reduced E10 for all four models on Commit0 and SlopCodeBench, with reported intervals excluding zero. On SWE-EVO the project-clustered comparisons were less decisive. Coverage-only feedback did not lower E10 and raised it in several SlopCodeBench comparisons. In Table 1 the individual held-out correctness intervals include zero. A joint mixed model on SlopCodeBench leaves a possible cost of combined feedback.
- **Interpretation.** Sensitivity to inlining, variation across models and tasks, and one language and harness limit the claim. The study measures structure during the run. Continued maintenance of larger codebases remains open.

## Application and free check

Proposed. Keep tasks, prompts, budgets and the final test suite fixed while comparing reminder-only and complexity feedback. Read a sample of changed functions to see whether branching is simpler or has moved. Measure later change effort and test correctness alongside the concentration metric.

## Related note

- [Correctness and complexity](2016-correctness-and-complexity.md)

## Sources

- [arXiv record](https://arxiv.org/abs/2611.23817)
- [Inspected v1 text](https://arxiv.org/html/2611.23817v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
