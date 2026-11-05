**English** | [日本語](2026-rivet-multiturn-llm-routing.ja.md)

# RIVET: accuracy and cost in multi-turn LLM routing

## Overview

- Preprint on selecting an LLM at each turn of a multi-turn interaction.
- RIVET uses observed responses only during training and reports better MINT accuracy at lower call cost than its comparison router.
- The evidence comes from selected benchmarks and model pools; production gains remain untested.

## Practical reading (7 lines)

- A multi-turn agent can change models as the task evolves.
- RIVET routes from pre-call state while using logged responses as an auxiliary training signal.
- On MINT Test-141 it reports 87.94% accuracy and 74.7% lower total call cost than MTRouter.
- That reduction is conditional on the paper's evaluation, not a universal saving.
- A deployment study should measure success, price, latency, and switching together.
- Re-evaluate the accuracy–cost frontier on local workloads before adoption.
- The authors call for further controlled tests to isolate the causal contribution of response content.

## Source and verification scope

Haotian Yan et al., arXiv:2610.23239v2, 2026-10-20. Primary HTML methods, main table, conclusion, and data appendix checked on 2026-11-06 JST. Partial reading; no reproduction.

## Method, claims, and evidence

RVE scores candidate models before a call; training-only RIVE also sees the realized response, sharing a representation. MINT uses 200 training, 35 validation, and 141 test tasks, with MuSiQue, DROP, and MMLU-Pro as additional comparisons. On MINT, RIVET Online reports 87.94% accuracy and relative cost 0.199 versus MTRouter's 85.11% and 0.788. Cost is total API-call cost relative to the table's reference model.

## Limitations and open questions

Results depend on candidate models, prices, and task mix. On MuSiQue, online adaptation saves cost but has lower exact match than the offline variant. Further controls are needed to attribute gains specifically to response information.

## Comparison with related notes

Compare with existing LLM infrastructure notes on cost-efficiency measurement.

## Low-cost verification plan and use status

Proposed, not performed: compare a fixed model with turn-level selection on a small public multi-turn task set, recording success, cost, and latency.

## Primary source

- [Specified primary source](https://arxiv.org/html/2610.23239v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
