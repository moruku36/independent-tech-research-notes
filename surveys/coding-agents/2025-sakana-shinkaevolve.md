**English** | [日本語](2025-sakana-shinkaevolve.ja.md)

# ShinkaEvolve: sample-efficient program search with LLMs

## Overview

- **What it is** A Sakana AI preprint on evolutionary search over programs proposed by LLMs.
- **What it says** A program archive, novelty filtering, and adaptive model selection reduce redundant evaluations.
- **Caveat** The reported evaluation count is specific to the task and leaves total run cost unresolved.

## Practical reading (six lines)

- Start with a scored program and use archived variants as parents for new candidates.
- Reject similar proposals before running the numerical evaluator.
- Update model selection according to the improvements its proposals yield.
- The authors beat AlphaEvolve's reported 26-circle packing score within a budget of 150 evaluations.
- For a local comparison, count proposals, evaluations, runtime, and cost separately.
- Use held-out cases because the search directly optimizes the evaluator.

## Source and reading scope

Robert Tjarko Lange, Yuki Imajuku, and Edoardo Cetin, *ShinkaEvolve: Towards Open-Ended And Sample-Efficient Program Evolution*, arXiv:2509.19349v1, submitted September 17, 2025. On November 20, 2026 JST, partially read the method, results, ablations, and limitations and checked the public code landing page. Independent replication was not checked.

## Evidence and limitations

- **Circle packing (§4.1).** Maximize the sum of the radii of 26 non-overlapping circles in a unit square. The result compares the achieved objective to AlphaEvolve's reported solution. The evaluation budget does not quantify total proposal calls or equalize hardware and total cost.
- **AIME (§4.2).** The search evaluated candidates on 30 AIME 2024 questions, with three runs per candidate, over 75 generations using gpt-4.1-nano. The selected scaffold uses seven calls per question. The reported 2023 and 2025 transfer evaluations are separate from this search budget.
- **ALE-Bench LITE and MoE (§§4.3–4.4).** Across ten tasks, private-test scores improved by about 2.3% on average over the ALE-Agent starting solutions after public-test search. The MoE experiment searches for a load-balancing loss using a 556M-parameter model and tests transfer at 2.7B. The framework needs human-designed numerical objectives, and the authors identify API costs as a practical limit.

## Application and free check

Proposed and untried. Compare fixed-budget search with and without duplicate filtering on a small deterministic optimization problem. Use prewritten candidate variants so the first check needs no API calls. Reserve test instances and record valid proposals, evaluator calls, runtime, and final objective.

Usage status is proposed. No inference or replication runs were performed.

## Related note

- [Darwin Gödel Machine](2025-sakana-darwin-godel-machine.md)

## Sources

- [Primary report, arXiv v1](https://arxiv.org/html/2509.19349v1)
- [Sakana AI code repository](https://github.com/SakanaAI/ShinkaEvolve)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
