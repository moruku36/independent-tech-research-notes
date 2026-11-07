**English** | [日本語](2024-sakana-ai-scientist.ja.md)

# The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery

## Overview

- Research article and associated paper on the 2024 pipeline linking ideas, code, experiments, writing, and automated review.
- Starting from supplied ML templates, it produces manuscripts and experimental artifacts.
- High automated-review scores do not establish conference acceptance; implementation, comparisons, and interpretation can be flawed.

## Practical reading (7 lines)

- The AI Scientist is the 2024 pipeline connecting research ideas with experiments and paper writing.
- It starts from human-provided code and a research domain, then searches, implements, experiments, writes, and reviews.
- It generates papers and logs in diffusion modeling, language modeling, and grokking.
- The reported roughly $10–15 per paper reflects its historical constrained setup, not a current total-cost guarantee.
- Proposed application: audit one small hypothesis by aligning code changes, measurements, and manuscript claims.
- Distinguish an automated acceptance-like score from actual conference acceptance or independent replication.
- The original system can misimplement ideas and make unfair comparisons, requiring artifact review.

## Source and verification scope

- Supplied article: The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery, Sakana AI, 2024-08-13.
- Associated paper: same title, Chris Lu, Cong Lu, Robert Tjarko Lange, Jakob Foerster, Jeff Clune, David Ha. arXiv:2408.06292v3, 2024-09-01; first submission 2024-08-12. Venue not checked.
- Checked 2026-11-07 JST: article text and primary HTML methods (§3), reviewer (§4), experiments (§6), limitations (§8), and cost discussion (§9), partially. Generated papers, figures, and code not exhaustively audited or executed.
- Status: primary sources checked, partially read, not reproduced. The article and paper form one record. Results from the successor AI Scientist-v2 are separate.

## Research question

How far can LLMs carry out research ideation, experimentation, writing, and evaluation from an existing ML experiment codebase?

## Method, data, and comparison conditions

Aider edits human-provided experiment templates, iterates experiments, and produces LaTeX manuscripts. Semantic Scholar supports novelty checks and citations; an LLM reviewer assigns scores. Evaluation spans three ML templates and multiple models (§3, §6).

## Claims and evidence

The authors report completed papers, automated-review scores, and costs, plus generated-paper case studies. The reviewer is evaluated on 500 ICLR 2022 papers; a generated paper's score remains that reviewer's judgment. Roughly $10–15 per paper reflects the historical configuration and constrained experiments (§4, §6, §9).

## Limitations and threats to validity

Humans set templates and domains. Failure modes include incomplete artifacts, wrong implementations, unfair compute comparisons, numerical interpretation, and inability to inspect figures visually. Reviewer evaluation may involve training-data contamination and submission-versus-camera-ready differences. Costs do not generalize to other fields or large experiments. These are not independently validated discoveries.

## Comparison with related work

[Open-ended research evaluation](../agent-safety/2026-open-ended-ai-research-shadow-evaluation.md) separately assesses research progress; distinguish completing a paper pipeline from making a contribution. [DGM](2025-sakana-darwin-godel-machine.md) optimizes the agent design itself.

## Free-to-run verification plan and usage status

Proposed, not performed: select one released paper and map its claims to logs and code. Begin with artifacts that require no API calls; retain uncomputed results as unverified. Usage status: proposed.

## Open questions and next checks

Check artifact commits, comparison conditions, novelty judgments, and cost breakdown.

## Primary sources

- [Supplied research article](https://sakana.ai/ai-scientist/)
- [Associated paper metadata](https://arxiv.org/abs/2408.06292)
- [Paper version examined](https://arxiv.org/html/2408.06292v3)
- [Released code (not executed)](https://github.com/SakanaAI/AI-Scientist)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
