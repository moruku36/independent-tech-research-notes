**English** | [日本語](2026-apertus-llm-confidentiality-reasoning.ja.md)

# Apertus red-teaming: confidentiality across languages and reasoning modes

## Overview

- A preprint assessing whether system-prompt confidentiality instructions protect third-party records in Apertus v1.5 and five other model families.
- Experiments in six request languages found disclosure in model outputs, including reasoning traces when the final response withheld the record.
- The paper measures outcomes under a synthetic setup that uses the system prompt as its only control. Production incidence remains unmeasured.

## Six practical takeaways

- The study placed synthetic records in model context and compared outcomes across languages and reasoning modes.
- In one indirect-disclosure test, the reported leakage rates were 96% for Apertus 8B and 95% for 70B under the paper's conditions.
- Confidential facts could surface even when outputs omitted identifiers, and reasoning traces could contain data absent from the final answer.
- The Apertus checkpoint comparison showed that safety did not improve consistently across post-training stages.
- Practical implication: enforce per-user access before retrieval results reach the model, and treat reasoning traces and their logs as potentially sensitive.
- Deterministic runs, automated adjudication, and machine-checked translations limit generalization. Repeated variants also share underlying test cases.

## Source and verification scope

- Evidence status: primary source checked. Read the method, reported results, conclusion, and limitations in arXiv v1. No independent replication.
- Bibliography: Hatef Otroshi Shahreza, *Red-Teaming a Sovereign LLM, Its Reasoning and Its Training Stages*, arXiv:2611.32710v1, 2026-11-24. Checked 2026-11-28.
- Source: [arXiv record](https://arxiv.org/abs/2611.32710) · [v1 full text](https://arxiv.org/html/2611.32710v1).

## Evaluation and scope

The synthetic data covered deployment scenarios such as health, employment, and public services. The six request languages were English, German, Swiss German, French, Italian, and Romansh. Authorization and filtering outside the model were absent by design. The paper separately covers attribution and representation. This note focuses on confidentiality.

## Evidence and interpretation

The headline percentages apply to one test class for two model sizes. The authors report reduced effective sample size from related variants and caution that the benchmark is scenario-specific. The results support defense in depth before inference and in observability.

## Related note

[OpenAI’s frontier AI risk controls from training to deployment](2026-openai-frontier-risk-model-lifecycle.md) describes safety controls at several points in the model lifecycle. The Apertus study supplies concrete reasons to revisit confidentiality coverage after model changes.

## Proposed check

Using a local mock with two synthetic accounts, check that the retrieval service only passes allowlisted records for the signed-in account. Inspect configured destinations and access rules for outputs and traces. Status: proposed. Production controls and cross-language performance remain unverified.
