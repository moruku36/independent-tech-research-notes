**English** | [日本語](2026-evolving-agent-teams.ja.md)

# Evolving Agent Teams

## Overview
- **What it is:** An experimental preprint that dynamically restructures agent roles and coordination for GPU kernel optimization.
- **What it reports:** On four GPU kernel tasks, the authors report better results than a single coding agent under matched budgets.
- **Caveat:** Few runs and unresolved inconsistencies in fixed-team results and model descriptions limit interpretation.

## Source and scope
Shiyi Cao, Ziming Mao, Dacheng Li, Joseph E. Gonzalez and Ion Stoica, [Evolving Agent Teams](https://arxiv.org/html/2610.36848v1), arXiv:2610.36848v1, 27 October 2026. Checked 1 November 2026 JST: selected primary HTML sections, methods, main experiments, conclusion and parts of appendices. The paper links [author code](https://github.com/caoshiyi/EAT); code and PDF were not examined and reproduction was not performed.

## Question and method
Kernel optimization can plateau when agents continue tuning an easy but architecturally limited direction. A supervisor diagnoses stagnation and changes roles, coordination and knowledge management. A shared persistent filesystem stores learnings, artifacts and evolution history for subsequent teams. The main experiments use Claude Code with Claude Opus 4.6 on four H100 and B200 kernel tasks.

## Results and conditions
- For MLA decode under a matched budget, the authors report approximately 0.44–0.51× for single-agent Claude Code and 0.75× for the evolving team relative to the production FlashInfer kernel; values below 1× are slower than that baseline.
- With **additional budget**, an H100 MLA kernel achieved about 1.21× geometric mean speedup over the production FlashInfer baseline on 47 FlashInfer-Bench workloads, faster on 36 and 0.86–0.99× on the other 11. The authors report passing the 47 correctness tests. This is separate from the matched-budget comparison.
- Speedup is the geometric mean of baseline latency divided by candidate latency. Treatment of FlashInfer planning affects the baseline; Figure 1 reports 0.96× against the plan-excluding baseline.
- Main settings were run twice with the better result reported; fixed-team and Codex ablations and additional case studies used single runs. Statistical conclusions are limited.

## Unresolved inconsistencies in the paper
- The introduction reports **0.55×** for the fixed four-role MLA team, while Section 4.5 reports **0.31×**; the reason is not established.
- Section 4.1 describes the fixed team as **Opus 4.7** and the proposed system as **Opus 4.6**, whereas Section 4.5 says they use the same model. The isolated effect of restructuring cannot be assumed.
- The extended-budget GEMM+AllReduce result is stated as **1.49×** in Section 4.2 and **1.56×** in Section 4.3. A condition difference was not confirmed; the discrepancy remains unresolved.

## Proposed applications
In an AI team or home lab, try a small loop: diagnose the bottleneck, adjust roles, and retain failed attempts, changes, performance and cost. Compare against a single-agent baseline with matched budgets. Design permissions, secrets, approvals and audit separately. This is a proposal, not a validated cloud-operations result.

## Related work and limitations
[Minimal harness for autonomous ML engineering](2026-ml-engineering-minimal-harness.md) finds a strong single-session baseline on different ML benchmarks. The tasks and setups differ, so their findings are not directly comparable. The authors note few runs, lack of detailed cost–performance analysis, and no controlled evaluation in noisier domains. No independent validation, reproduction or adoption.

[Coding agents index](README.md)
