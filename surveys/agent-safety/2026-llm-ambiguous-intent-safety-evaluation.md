**English** | [日本語](2026-llm-ambiguous-intent-safety-evaluation.ja.md)

# Ambiguous intent in LLM safety: filter evidence and legitimate use

## Overview

- **What it is** A preprint on LLM safety when a request admits both legitimate and harmful interpretations.
- **What it says** In the tested settings, surface resemblance to ordinary requests was associated with filter pass rates.
- **Caveat** The study leaves the tested filter’s false-positive rate on benign requests unresolved.

## Practical reading (six lines)

- Treat intent judgments from text as uncertain.
- The paper evaluates 11 models and three datasets in single-turn settings.
- Its response-only automated judge labels unsafe outputs under a specified rubric.
- Filter pass rates and output-level unsafe-response rates answer different questions.
- An anonymous survey of 95 valid responses found differing preferences across seven requests.
- For defense evaluation, measure unsafe output and usefulness to legitimate users together.

## Source and reading scope

Wenzhuo Xu et al., *LLMs are Vulnerable to Malicious Requests with Indistinguishable Intent*, arXiv:2611.17818v1, November 13, 2026. On November 20, 2026 JST, checked the metric, defense results, discussion and user study. Independent replication was not checked.

## Evidence and limitations

- **Metrics (§§3.2, 6.3–6.4).** The unsafe-output judgment does not establish real-world accuracy or actionability. The proposed input filter blocked many of the evaluated requests. The authors did not measure its false-positive rate on ordinary requests or isolate the mechanism behind the reported association.
- **Survey (§7).** Of the 95 respondents, 66.3% recalled a refusal they considered unwarranted. This is self-reported experience and cannot estimate the proposed filter’s error rate.

## Application and free check

Proposed and untried. Use harmless synthetic support requests with a mock permission boundary. Compare clarification and bounded replies for reviewer-rated usefulness, and measure incorrect approvals and refusals in the mock policy settings.

Usage status is proposed. No replication was performed.

## Related note

- [Refusal as a model-specific direction](2024-refusal-single-direction.md)

## Sources

- [Primary report, arXiv v1](https://arxiv.org/html/2611.17818v1)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
