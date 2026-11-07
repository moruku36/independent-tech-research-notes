**English** | [日本語](2026-agents-claude-instruction-file-census.ja.md)

# What Open-Source Projects Tell Their Coding Agents: A Census of AGENTS.md and CLAUDE.md

## Overview

- Observational preprint surveying root instruction files in popular, active GitHub repositories.
- It finds target files in 26.3% of 22,854 repositories, mixing project knowledge and workflow rules, often without rationale.
- Presence is not runtime use or effectiveness, and model annotations diverge from human judgments.

## Practical reading (7 lines)

- The study describes information and rules OSS projects put in AGENTS.md and CLAUDE.md.
- It covers 22,854 repositories with at least 1,000 stars, recent pushes, and further selection criteria.
- Target root files appear in 26.3%, covering project knowledge, testing, and workflow.
- Content estimates put 74.0% of directives without rationale, using model-assisted annotation.
- Proposed application: audit commands, conditions, reasons, and maintenance ownership in one's own files.
- File prevalence does not establish AI usage rates or improved development outcomes.
- Human validation uses one author and sixty statements; model agreement alone is not accuracy.

## Source and verification scope

- Original title: What Open-Source Projects Tell Their Coding Agents: A Census of AGENTS.md and CLAUDE.md.
- Author: Pawel Zarzycki.
- arXiv:2610.31715v2, 2026-10-26; first submission 2026-10-22. The revision comment reports abstract-metadata corrections with unchanged paper text. Venue unconfirmed.
- Checked 2026-11-08 JST: primary HTML methods (§3), results (§4), validity threats (§5), and human review (Appendix A.2). Original files and labels not exhaustively audited; searches and aggregation not rerun. Status: partially read.

## Research question

How common are agent instruction files in popular, active OSS projects, and what do they communicate?

## Method, data, and comparison conditions

The 2026-10-16 snapshot includes non-fork, non-archived repositories in thirteen primary languages, with ≥1,000 stars and a push within ninety days. Exact-case root files on default branches are located, references/deduplication resolved, and 341,852 statements model-extracted and coded. Headline content estimates use a weighted sample of 992 fully Sonnet-coded repositories; element tables/associations largely use uncorrected Haiku codes (§3).

## Claims and evidence

Target files occur in 6,006/22,854 repositories (26.3%), and 59.6% of the top star tier of 89. The 74.0% directive-without-rationale estimate and the 82.9% repository-with-any-rationale estimate have different denominators. AI-attribution policies also differ. These describe written content, not a ranking of effective rules.

## Limitations and threats to validity

Nested files and actual runtime consumption are outside scope. One author reviews sixty statements, with 43–50% subject-area and 32–37% fine-subject agreement. The check selects exact-span matches and stops early. Cross-sectional associations inherit annotation and population-selection errors and do not establish causal effectiveness.

## Comparison with related work

[Trojan Horse](../agent-safety/2026-trojanforge-repository-poisoning.md) measures repository execution risk; this study describes instruction documents. Presence and enforcement differ. Controlled studies such as [minimal ML harnesses](2026-ml-engineering-minimal-harness.md) address another question; this census does not show that more documentation improves performance.

## Free-to-run verification plan and usage status

Proposed, not performed: manually classify a small set of owned rules by target, command, reason, exception, and reference, checking duplicates and stale text. Assess any later revision on matched tasks and budgets. Usage status: proposed.

## Open questions and next checks

Audit source/label samples, obtain independent human judgments, examine nested scope, and repeat at later snapshots. Instruction examples in the paper are treated as study data.

## Primary sources

- [arXiv:2610.31715](https://arxiv.org/abs/2610.31715)
- [Primary HTML examined v2](https://arxiv.org/html/2610.31715v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
