**English** | [日本語](2025-conductor-natural-language-orchestration.ja.md)

# Conductor: learning natural-language coordination

## Overview

- **What it is** Research on training an LLM to generate multi-agent workflows.
- **What it says** A 7B Conductor learns subtask instructions, worker assignments and communication access through GRPO.
- **Caveat** Learned coordination needs training and bounded execution; current API models are not validated by these historical results.

## Practical reading (six lines)

- Each step contains a natural-language task, worker ID and access list for earlier outputs.
- The final workflow result supplies the training reward.
- Randomized worker subsets support customization within the studied pools.
- A recursive extension allows the Conductor to call itself.
- Reported quality/cost comparisons depend on task mix, prices and worker configurations.
- Proposed application: validate an explicit workflow schema before executing any delegated step.

## Source and reading scope

Stefan Nielsen, Edoardo Cetin, Peter Schwendeman, Qi Sun, Jinglue Xu and Yujin Tang. Learning to Orchestrate Agents in Natural Language with the Conductor. arXiv:2512.04388v5, 2026-05-06; first posted 2025-12-04. Checked 2026-11-15 JST, selected §§3–4 and efficiency discussion. ICLR 2026 status is metadata-reported; version differences unexamined.

## Evidence and limitations

Training uses 960 problems from four domains. Controlled comparisons use the same seven workers. Recursive evaluation increases available agent calls; its gain should not be attributed solely to topology at equal compute. Generalization to studied subsets does not establish arbitrary model compatibility.

## Related notes

- [TRINITY](2025-trinity-evolved-coordinator.md)
- [Fugu report review](2026-fugu-orchestration-report-review.md)

## Free check and usage status

Proposed, untried. First draft a free schema for tasks, allowed workers, dependencies, output contracts and call limits. Compare static routing and generated workflows later under matched total budgets, with separate recursion limits and held-out acceptance tests. Record parsing failures, invalid access, success and cost. Next inspect the trained checkpoint and reproducibility details; no RL or paid API calls were performed.

## Sources

- [Submitted source](https://arxiv.org/abs/2512.04388v5)
- [Inspected text](https://arxiv.org/html/2512.04388v5)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
