**English** | [日本語](2026-sakana-qd-rec-open-ended-recommendation.ja.md)

# QD-Rec: evolving diverse reasons for recommendations

## Overview

- **What it is:** Sakana AI research on recommending existing items together with reasons for choosing them.
- **What it says:** An evolving archive and adaptive item selection improve recommendation sets in many tested settings.
- **Caveat:** Judge scores are reused during search and reporting; gains do not establish factual correctness or real-world decision value.

## Practical reading (seven lines)

- A fixed pool of papers or companies can still support new hypotheses about why each item is useful.
- QD-Rec retains different reasoning angles and adapts earlier proposals instead of only sorting candidates once.
- A contextual bandit directs the next item evaluation; the foundation model is not retrained by this loop.
- Reported quality improvements vary by scenario and proposer, rather than dominating every comparison.
- Proposed application: attach several grounded experiment ideas to papers in this reading repository.
- Evaluate usefulness, factual support, and distinctness separately before adopting an idea.
- This note records a proposed trial; no model calls, implementation, or reproduction were performed.

## Source and reading scope

Takashi Ishida, Taro Makino, Issa Sugiura, *QD-Rec: Open-Ended Evolution of Recommendations via Quality-Diversity*, Sakana AI, arXiv:2610.23470v2 (2026-10-19; first submitted October 16). Preprint; peer-review acceptance not checked.

Checked **2026-11-17 JST**: supplied technical page, Japanese announcement (October 20), paper §§3–5 and selected appendix passages, and the code README/configuration/shared loop files at commit `3a04ed170583e14ca08e689e8bff8fddf267dc8e`. Partially read; not reproduced. The article, paper, and code are one research record.

## Question and mechanism

How can a limited evaluation budget produce useful alternatives with genuinely different reasons?

The [Japanese announcement](https://sakana.ai/qd-rec/) describes a loop over **item–hypothesis pairs**. An embedding-based bandit balances estimated quality and unexplored items; the proposer adapts, combines, or departs from archived ideas. Novel pairs enter the archive; other pairs must beat their closest neighbor in a blind comparison. Rejected evaluations still inform selection. Novelty admission can retain a weak proposal as a stepping stone.

This evolves recommendation artifacts, not model weights or the agent's implementation.

## Experiment and evidence

The [technical page](https://pub.sakana.ai/qd-rec/) reports M&A, synthetic-customer targeting, and paper recommendation; pools are approximately 6,300, 10,000, and 17,500 items. Runs use ten initial entries, 1,000 evaluations, and five seeds. Proposers are Sonnet 5 / Haiku 4.5, with GPT-5.6 Terra judging; embeddings are 512-dimensional.

Illustrative paper-recommendation results for the open-endedness profile, **mean quality ± standard error** (0–10):

| Proposer | Novelty | Novelty+Evo | QD-Rec |
| --- | --- | --- | --- |
| Sonnet 5 | 4.96 ± 0.02 | 5.26 ± 0.02 | 5.32 ± 0.02 |
| Haiku 4.5 | 4.26 ± 0.02 | 5.03 ± 0.07 | 4.87 ± 0.02 |

QD-Rec is not best in every cell. Its final quality uses scores already available during search, not an independent held-out judge. Embedding diversity and PCA-grid coverage also measure different properties.

The [paper](https://arxiv.org/html/2610.23470v2) additionally uses historical Goodreads ratings: these rate books, not the generated recommendation text. It estimates API costs by replaying sampled calls because original token usage was not logged; equal evaluation counts do not mean equal spend. Recommendation plausibility needs separate factual checking and current source data.

## Public code versus the experiment

The [code README](https://github.com/SakanaAI/QD-Rec) uses OpenRouter and defaults to GPT-6 Luna as both proposer and judge, unlike the paper's setup. It needs external model/embedding calls; M&A data require separate access. No zero-cost replication is established.

Inspected [paper configuration](https://github.com/SakanaAI/QD-Rec/blob/3a04ed170583e14ca08e689e8bff8fddf267dc8e/apps/papers/config.py) and [archive records](https://github.com/SakanaAI/QD-Rec/blob/3a04ed170583e14ca08e689e8bff8fddf267dc8e/shared/archive_records.py) distinguish item IDs from hypothesis-entry IDs and active/replaced/discarded states. A JSON file's total record count is not its final active archive size. Source inspection is not execution verification.

## Related notes and application ideas

These are conceptual comparisons, not matched benchmark results.

- [Darwin Gödel Machine](../coding-agents/2025-sakana-darwin-godel-machine.md): compare what is evolved—agent code versus item/reason pairs.
- [The AI Scientist](../coding-agents/2024-sakana-ai-scientist.md): use recommendation as a possible literature-selection stage; experiment execution and scientific validation still need their own process.
- [Adaptive branching MCTS](2025-sakana-adaptive-branching-mcts.md): compare exploration decisions and budget allocation; do not transfer its performance claims to recommendation.

## Free check and usage status

**Proposed / untried / not adopted.** A free preliminary check could use 20 existing notes and manually written hypotheses, without API calls. Fix a researcher profile and compare simple keyword ranking, random selection, and a hand-operated archive under the same review time. This checks whether keeping distinct rationales is useful; it does not reproduce the learned bandit or published scores.

Keep source IDs, evidence passages, hypothesis IDs, parents, decisions, and review reasons in a local ledger. Have a reviewer unaware of method labels assess groundedness, actionable experiments, duplication, and actual papers chosen. A later model-based trial should separately cap evaluations, tokens, money, and time.

Next checks: held-out human usefulness, sensitivity to judge/model changes, unsupported claims, batch reconciliation, and full data/licensing/reproduction requirements.

## Sources

- [Supplied technical page](https://pub.sakana.ai/qd-rec/)
- [Paper metadata and v2](https://arxiv.org/abs/2610.23470v2) · [Inspected text](https://arxiv.org/html/2610.23470v2)
- [Japanese announcement](https://sakana.ai/qd-rec/)
- [Code at the inspected commit](https://github.com/SakanaAI/QD-Rec/tree/3a04ed170583e14ca08e689e8bff8fddf267dc8e)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
