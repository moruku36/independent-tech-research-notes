# Why Does Structured Output Fail? An Empirical Study of Prompt-Enforced Pydantic Schemas Across Nine LLMs

[日本語](2026-structured-output-failure.ja.md) | [Theme index](README.md)

- **Source:** [arXiv:2610.33949v1](https://arxiv.org/html/2610.33949v1), preprint under review, 24 October 2026.
- **Author:** Amit Verma.
- **Scope:** Main text, methods and reported results reviewed; no independent code inspection or reproduction.

## Summary
This study examines why generated structured responses fail application validation and separates syntax, formatting and schema violations. Its results concern prompted Pydantic schemas, rather than provider-native constrained-output modes.

## Method and findings
Across 3,997 generation attempts in nine model/API configurations on HotpotQA and FinanceBench, the author analyzes validation failures. Of 681 responses with fenced JSON, 640 came from Haiku 4.5 and 41 from Sonnet 5. Offline fence removal made 327 of those 681 pass validation; 354 still failed, mainly because of field-length constraints. This is offline revalidation, not a production rerun. Error-specific retry feedback is proposed but not experimentally validated.

## Practical interpretation
In an agent pipeline, record parse errors separately from schema failures, validate input at the receiving boundary, and consider bounded retries with useful error feedback. Evaluate native structured-output controls separately for the actual provider and schema; the study did not measure those modes.

## Limits
Task, prompts, models, schemas and API versions constrain generalization. Fixing fences alone cannot fix semantic or field constraints; passing schema validation does not establish factual correctness.
