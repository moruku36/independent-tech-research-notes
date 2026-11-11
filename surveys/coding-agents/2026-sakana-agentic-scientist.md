**English** | [日本語](2026-sakana-agentic-scientist.ja.md)

# The Agentic Scientist and evidence-based research orchestration

## Overview

- **What it is** Sakana AI’s scaffold for computational research with coding agents.
- **What it says** It coordinates parallel investigation, baseline and ablation experiments, evidence aggregation and manuscript writing.
- **Caveat** Automated rubric reviews are proxy assessments. Novelty and independent reproduction remain important gaps.

## Practical reading (six lines)

- A task contract defines the candidate interface and evaluation procedures.
- Parallel workers explore hypotheses in separate workspaces and share distilled findings.
- Idea completion and improvement of the best program have separate acceptance checks.
- Selected results feed retrospective experiments and report writing.
- A proposed research harness records hypothesis, code version, evaluation and supporting artifact together.
- The authors identify incomplete task drafting and limited early literature search as limitations.

## Source and reading scope

Robert Tjarko Lange, Luca Grillotti, Yutaro Yamada, Rujikorn Charakorn and David Ha. arXiv:2610.18933v1, 2026-10-13. Checked 2026-11-12 JST, selected §§3, 5 and 8. Implementation and experiments were not run.

## Method, evidence and limitations

The study reports research case studies and 70 campaigns over five manually prepared tasks. Its AI manuscript reviews complement search metrics. One co-created paper’s conference acceptance supplies a different kind of evidence. The report calls for independent reproduction and better assessment of novelty.

## Related notes

- [The AI Scientist](2024-sakana-ai-scientist.md)
- [Organon](2026-organon-scientific-discovery.md)

## Free check and usage status

Proposed, untried. For one small deterministic experiment, write the hypothesis and reserve a final test before exploration. Record unsuccessful trials too, then compare the selected result against a fixed baseline. Next inspect task contracts, compute budgets and judge independence before a pilot.

## Primary sources

- [arXiv record](https://arxiv.org/abs/2610.18933)
- [Inspected v1](https://arxiv.org/html/2610.18933v1)
- [Linked implementation](https://github.com/SakanaAI/AI-Scientist-v3)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
