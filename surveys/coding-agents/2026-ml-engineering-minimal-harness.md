**English** | [日本語](2026-ml-engineering-minimal-harness.ja.md)

# How Much of a Harness Does a Strong Agent Need for Autonomous ML Engineering?

## Overview
- **What it is:** An experimental preprint comparing scaffolding for autonomous ML engineering.
- **What it says:** With strong backbones, a minimal single long-session agent is a strong baseline against the tested harnesses.
- **Caveat:** Results apply to selected ML benchmarks, models and budgets; they do not establish that security controls are unnecessary.

## Source and scope
Kirill Brilliantov, Alejandro Hernández-Cano and Emmanuel Abbé, [arXiv:2609.40303v1](https://arxiv.org/html/2609.40303v1), 30 September 2026. Selected primary HTML sections, experimental setup, results, limitations and portions of appendices checked on 1 November 2026 JST. PDF and implementation code not checked; no reproduction.

## Question and method
A harness supplies tooling, search or orchestration around an agent. The authors compare a minimal long-running OpenCode-based single session called Malena with ablations and published multi-component harnesses. Their main external comparison uses 30 corrected MLE-bench tasks (fixed30), matched backbones, time and compute, including 24 hours and one A100 80 GB GPU. Self-selected submissions are distinguished from oracle-best selection; a smaller NatureBench evaluation is also reported.

## Results and interpretation
For strong models, the authors report that none of the tested external harnesses significantly outperformed Malena on the measured comparison. Direct execution and filesystem access improved performance over a chat-only setting. For GLM 5.2 on fixed30 at 24 hours, they report 62.5% any-medal rate for Malena versus 47.1% for the best external harness. This is a macro average across 30 tasks after averaging runs within each task, not a production success rate. With weaker Gemma 4 31B an external harness significantly exceeded Malena on percentile. Lack of statistical significance does not establish exact equivalence.

## Proposed applications
Use a single agent with explicit execution and logging as a baseline for ML experiments, and compare added orchestration under matched model, time and resources. Measure cost, reproducibility and submission selection. Maintain access controls, approvals, audit and secret protection as separate requirements. These are proposals and have not been validated in the user's environment.

## Limits and next checks
Public Kaggle tasks create possible contamination; confidence intervals can be wide; tuning effort may differ between authors' system and external systems; sophisticated multi-agent coordination was not fully explored. Authors applied contamination checks and a supplementary benchmark, but generalization remains limited. The 24-hour experiments used 3–4 seeds per task. No independent implementation, reproduction or adoption.

[Coding agents index](README.md)
