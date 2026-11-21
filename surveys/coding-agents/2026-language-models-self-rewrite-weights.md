**English** | [日本語](2026-language-models-self-rewrite-weights.ja.md)

# Language models editing their own weights: independent trials and held-out gains

## Overview

- **What it is**: A preprint on whether a model can propose and evaluate direct edits to its own weights without gradient-based training.
- **What it says**: In the second protocol, one Qwen3.5-27B edit raised reported accuracy from 57.2% to 63.8% on 490 held-out math problems. Another experiment repaired a deliberately damaged copy.
- **Caveat**: Each editing session started from the original weights. The eight sessions show a sequence of replacement candidates on one setup.

## Practical reading (six lines)

- The researchers gave the model graded practice answers and tools to inspect, edit and test a checkpoint within a bounded session.
- The 27B model proposed direct weight changes and evaluated them with forward passes. The framework performed an additional practice check before submission in the second protocol.
- On 490 held-out problems with eight answers per problem and matched seeds, session 8’s edit raised accuracy from 57.2% to 63.8%, or 6.6 percentage points.
- Of the eight sessions, three submitted an edit and five withdrew. Each began with the original weights, and the reported sequence replaces the accepted candidate when a new edit is submitted.
- In a separate damage experiment, the 27B model repaired a deliberately corrupted copy. The tested smaller Qwen3.5 variants did not show comparable gains.
- Proposed application: review changes against a frozen baseline using a versioned evaluation set and disjoint practice and final checks.

## Source and reading scope

*Language Models Can Rewrite Their Own Weights*, Jiajun Fan, Neil He, Changyi Yang, Andy Mao, Xi Zhu, Chaoran Cheng, Kaiqu Liang, Shuaike Shen, Zetian Li, Ruihan Guo and Ge Liu. arXiv:2611.21885v2, revised November 18, 2026. Checked November 22, 2026 JST, with emphasis on Sections 2–3, Figure 16, Tables 2 and 13, and Appendices D.3 and E.9. No checkpoint edits or independent replication were performed.

## Evidence and limitations

- **Task and evaluation.** The framework gives models from one Qwen3.5 family access to weights, graded math answers and a restricted set of tools. Candidates are checked with forward passes. The second protocol reserves practice items for an additional framework-run check before the model submits or withdraws. The final comparison pairs the original and edited runs on the same questions and seeds, with up to 16,384 tokens per answer.
- **Changes to the original model.** The first protocol’s 27B edit raised held-out accuracy by 1.1 percentage points. In the second protocol, the three submitted edits scored gains of 0.5, 4.0 and 6.6 points, respectively, with the smallest result statistically inconclusive. The 6.6-point gain has a reported 95% interval of 5.0–8.1 points. Answers reaching the token limit fell from 33.6% to 26.1% for the most successful edit. This supports an improvement on the evaluation as scored under its token limit.
- **Repair and transfer.** In the separate fault experiment, the intact 27B model proposed a repair to a deliberately corrupted copy, with only damaged weights available to the editing tools. It recovered from 0.0% to 33.0% on the held-out text problems, against 58.5% for the intact baseline. The text-derived repair raised accuracy across six selected image benchmarks from 7.3% to 70.2%. This transfer concerns the repair of the constructed fault.
- **Limits.** The original-weight edits used one model family and primarily math tasks. The sessions used a common original checkpoint and compared independent candidate edits. Effects on other architectures, wider capabilities, and repeated editing of an already edited checkpoint remain open.

## Application and free check

Proposed. Use a local spreadsheet or a short script with fictional answers to practice paired scoring over multiple seeds. Freeze the baseline and test set, record improvements and regressions by category, and keep candidate selection separate from final scoring. This exercises the evaluation design without changing model weights.

## Related notes

- [Frozen-weight self-improvement and failure traces](2026-frozen-weight-failure-trace-lessons.md)
- [Regression-aware harness updates](2026-guard-regret-guided-harness-improvement.md)

## Sources

- [arXiv record](https://arxiv.org/abs/2611.21885)
- [Inspected v2 text](https://arxiv.org/html/2611.21885v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
