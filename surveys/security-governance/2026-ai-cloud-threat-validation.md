**English** | [日本語](2026-ai-cloud-threat-validation.ja.md)

# Evidence for AI-discovered cloud threats

## Overview

- **What it is** Study of AI-generated cloud threat claims and their empirical validation.
- **What it says** Among 233 claims it labels 103 confirmed, 34 refuted, 44 conditional and 52 indeterminate.
- **Caveat** Its 75.2% precision uses only 137 resolved claims. Recall and full attack-chain success are outside that estimate.

## Practical reading (six lines)

- Three models propose threats for two architectures across three clouds.
- The study evaluates claims against the corresponding deployed testbeds.
- Precision is 103 divided by 103 plus 34.
- Conditional findings change the asserted mechanism while retaining a demonstrated impact.
- Combined model output increases coverage, while agreement alone is a weak confidence signal.
- A proposed review ledger links each claim to prerequisites, evidence and unresolved conditions.

## Source and reading scope

Nicholas Pecka, Lotfi Ben Othmane and Renee Bryce. arXiv:2611.10947v1, 2026-11-07. Checked 2026-11-13 JST, selected methodology, outcome tables and limitations.

## Method, evidence and limitations

Validation combines environment evidence, model review and expert adjudication. Confirmed prerequisites can be weaker evidence than a complete attack demonstration. The testbeds omit some flows, and no complete threat inventory supports recall measurement. The scope is cloud infrastructure claims.

## Related notes

- [Multi-cloud security architecture](2026-multi-cloud-security-architecture.md)
- [CWE-bench](../coding-agents/2026-cwe-bench-defensive-repair.md)

## Free check and usage status

Proposed, untried. Review an owned architecture on paper using synthetic findings. Mark claims confirmed, refuted, conditional or unresolved and record the evidence needed to change each verdict. Next examine human-review agreement and representativeness. Live testing and deployment were not performed.

## Primary sources

- [Versioned record](https://arxiv.org/abs/2611.10947v1)
- [Inspected full text](https://arxiv.org/html/2611.10947v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
