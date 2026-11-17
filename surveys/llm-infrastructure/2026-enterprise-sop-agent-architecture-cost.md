**English** | [日本語](2026-enterprise-sop-agent-architecture-cost.ja.md)

# Enterprise SOP agents: cost–success trade-offs and inconsistent reporting

## Overview

- **What it is**: A controlled preprint comparing single-agent, skills, orchestration, and swarm configurations.
- **What it says**: Added architecture brings substantial overhead; implementation and workload matter.
- **Caveat**: The v1 body and conclusion disagree on workload counts and headline results.

## Practical reading (six lines)

- The question is whether extra agent architecture earns its added cost.
- The main comparison fixes an Opus model and mock-tool behavior across eight arms.
- Its reported success/cost ordering varies with the SOP and implementation.
- Proposed use: establish a simple baseline before testing additional coordination.
- Audit output parsing, task denominators, and per-workflow outcomes before ranking designs.
- Treat the conflicting v1 figures and provisional orchestration cells as unresolved.

## Source and reading scope

Subhrangshu Nandi et al., *Agent Architecture Cost-Success Trade-offs: A Controlled Evaluation across Enterprise-Style SOPs*, arXiv:2611.12953v1, 2026-11-07. Checked 2026-11-18 JST: HTML §§3–5, tables, scoring caveats; PDF text confirms the conclusion discrepancy. Partially read; artifacts not rerun; venue not verified.

## Evidence and limitations

The body specifies 13 SOPs, 2,124 tasks per arm, and one fixed Claude Opus 4.8 model. Main macro success is 67.4% for the baseline and 75.6% for redesigned orchestration; §5 instead gives 12 SOPs and 65.6%/74.4%. The token/latency ranges also change. Preserve these conflicting versions rather than selecting a definitive headline.

§4.7 flags scoring defects and provisional orchestration multi-field cells. The authors' paired exception does not establish a universal aggregate ranking. Mock tools and one model family further limit transfer. More tasks within a workflow do not remove uncertainty across only a small number of workflows.

## Application and free check

Proposed / untried. A free preliminary audit can replay hand-written tool/output fixtures through an independently specified scorer. Include missing fields, aliases, early exits, and partially correct results; keep the denominator fixed to all tasks. This checks the evaluator, not the paper's agent performance. A later local trial should compare baseline, skill guidance, and coordination under matched inputs, tracking workflow-level success, tokens, latency, calls, abstentions, and maintenance effort. Seek corrected tables and code before reproducing the headline comparison.

Usage status: proposed / untried / not adopted. No model calls, environment changes, or experiments were performed for this note.

## Related notes

- [Task–architecture alignment](2025-scaling-agent-systems.md)
- [Model–harness evaluation](../coding-agents/2026-frontierharness-eval-v1-1.md)

These are reading comparisons, not matched performance evaluations.

## Sources

- [Submitted paper / 指定論文](https://arxiv.org/abs/2611.12953)
- [Inspected HTML v1 / 確認したHTML](https://arxiv.org/html/2611.12953v1)
- [PDF v1 / 不整合を確認したPDF](https://arxiv.org/pdf/2611.12953v1)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
