**English** | [日本語](2026-society-of-ai-scientists.ja.md)

# A Society of AI Scientists: collaboration, review, and evidence

## Overview

- **What it is** An alphaXiv report on a twelve-week deployment of research agents.
- **What it says** Agents shared studies, critiques, and corrections. Some reviews tested the claims against submitted artifacts.
- **Caveat** The deployment was observational, and the public dataset counts differ from the paper’s totals.

## Practical reading (six lines)

- From August 19 to November 12, 2026, the paper reports 936 agents and 936 studies across 35 laboratories.
- Humans supplied compute, budgets, and broad topics. Agents selected specific hypotheses and analyses.
- Link reported numbers to code and outputs, then verify whether the experiment supports the claim.
- In an agent-run journal, executing referee objections exposed conclusions that did not hold up.
- In 202 matched pairs scored by two LLM judges, agent papers led on rigor and human work led on novelty and significance.
- Before reproducing any aggregate, reconcile the paper’s cohort with the dataset snapshot.

## Source and reading scope

Rehaan Ahmad et al., *A Society of AI Scientists*, alphaXiv technical report, November 2026. On November 20, 2026 JST, checked the paper PDF’s deployment, review, matched comparison, and limitations sections and the public dataset card. No replication or archive-wide audit was performed.

## Evidence and limitations

- **Review and scoring (Figures 11 and 15).** In one journal audit, 77 of 156 executed major objections overturned the headline conclusion across a selected pool of papers. This denominator counts objections. The overall score advantage in the blinded prose comparison was driven by the founding laboratory. Cohort audits checked reported numbers against saved outputs, leaving experimental validity to separate review.
- **Dataset coverage (paper introduction and dataset card).** The PDF reports 936 studies. The November 17 snapshot card lists 916 studies total, with 881 flagged as in the paper’s time window, and says it excludes raw data, result archives, run logs, and checkpoints. The checked sources leave the discrepancy unresolved.

## Application and free check

Proposed and untried. With a small local example, record one claim, the specific output behind it, and the check that would falsify it. Track outcome consistency and design validity separately.

## Related note

- [The Agentic Scientist](2026-sakana-agentic-scientist.md)

## Sources

- [alphaXiv](https://www.alphaxiv.org/abs/2611.society-ai-scientists)
- [Primary report PDF](https://www.alphaxiv.org/abs/2611.society-ai-scientists.pdf)
- [Public dataset card](https://huggingface.co/datasets/alphaXiv/AgentAlphaXiv#matching-the-paper)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
