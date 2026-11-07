**English** | [日本語](2026-trojanforge-repository-poisoning.ja.md)

# Trojan Horse: Automated Repository Poisoning against Coding Agents

## Overview

- Preprint evaluating malicious repository code triggered during ordinary development workflows.
- TrojanForge generates attacks; successful cases form TrojanBench for cross-model and cross-harness replay.
- Success rates depend on curated projects, repeated attempts, and historical configurations, not general deployment incidence.

## Practical reading (7 lines)

- The study examines repository code executed as a side effect of legitimate development.
- TrojanForge uses code structure, execution paths, and target feedback to evaluate attack candidates.
- Four malicious-effect categories are tested; 384 successful cases form TrojanBench.
- Table 1 reports 71.6% overall ASR under a process permitting repeated attempts.
- Proposed defense: isolate unfamiliar project execution and restrict secrets and outbound connectivity.
- Audit code, actual execution, and side effects rather than relying only on textual-instruction screening.
- Historical product/model configurations do not establish a ranking of current products.

## Source and verification scope

- Original title: Trojan Horse: Automated Repository Poisoning against Coding Agents.
- Authors: Xiao Yang, Jinchang Hou, Jiawei Chen, Zhonghou Lv, Junyuan Shang, Chenfu Bao.
- arXiv:2610.23109v1, 2026-10-16; venue unconfirmed in checked metadata.
- Checked 2026-11-08 JST: primary HTML setup (§3), method (§4), results (§5), experimental settings (Appendix C), and verdict conditions (Appendix B), partially. Attack code and poisoned repositories were not downloaded or executed; no independent attack reproduction. Status: partially read.

## Research question

How effective are task-aware automated repository attacks and their transfer across agent configurations?

## Method, data, and comparison conditions

The authors curate 136 benign projects, assigning 34 to each of four harnesses. Development-context tasks and four malicious-effect categories are tested. AST and execution records guide candidate construction, followed by iterative evaluation. Verdicts rely on observable effects and detection conditions rather than only LLM judgments (§3–5, Appendices B–C).

## Claims and evidence

Table 1 records 384 successes among 536 valid repository-by-carrier conditions, or 71.6%; backdooring accounts for 130/136. These are outcomes of an iterative generation process, not single-command probabilities. TrojanBench contains the 384 successful cases and is replayed across four harnesses and twelve models. Its transfer rates are conditional on initial success.

## Limitations and threats to validity

Projects and executable-test entry points are selected, and tasks are model-synthesized. The attacker can modify the repository and test against the target. Default harness comparisons also change backbone models, so their differences cannot be attributed solely to harnesses. Matched-backbone replay must still respect source and carrier conditions. Selection, repeated attempts, and historical settings limit generalization.

## Comparison with related work

[Tool-invocation attacks](2025-tool-invocation-coding-agent-redteam.md) alter external tool descriptions/results; this study targets repository execution paths. [Kubernetes containment](../security-governance/2026-kubernetes-autonomous-agent-containment.md) proposes enforcement outside the model. These are not direct performance comparisons.

## Free-to-run verification plan and usage status

Proposed, not performed: use harmless markers in a synthetic project to trace executed files and write targets. Tabulate code changes, isolation boundaries, and egress restrictions without malicious payloads or attack generation. Usage status: proposed.

## Open questions and next checks

Check denominators/exclusions, product versions, the relationship between attack outcomes and task completion, and matched defensive controls. Do not interpret reported ASR as production compromise probability.

## Primary sources

- [arXiv:2610.23109](https://arxiv.org/abs/2610.23109)
- [Primary HTML examined v1](https://arxiv.org/html/2610.23109v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
