**English** | [日本語](2026-eb-mas-auditable-beliefs.ja.md)

# EB-MAS and auditable belief updates

## Overview

- **What it is** Agent-safety research on recording and controlling evidence-based commitments.
- **What it says** EB-MAS structures sources, claims and candidate updates, then checks updates before committing them.
- **Caveat** The paper includes prototype and supplementary tests. Production grounding and generalization remain open.

## Practical reading (six lines)

- Belief is an engineering representation of commitments guiding later action.
- The system records evidence and provenance in a graph.
- Update proposals pass through verification before commitment.
- Evaluation includes unsafe acceptance and benign false blocking.
- Source dependence matters when several agents repeat the same claim.
- A proposed harness trial audits updates across rounds using synthetic evidence.

## Source and reading scope

Zhuoyun Li, Boxuan Wang, Jinwei Hu, Xiaowei Huang and Yi Dong. arXiv:2610.38869v1, 2026-10-28. Checked 2026-11-13 JST, selected §3 and Appendices A–B.

## Method, evidence and limitations

The appendix reports multimodal and tool/memory prototypes plus calibrated and multi-round comparisons. Early ASB cases have strong provenance cues. Later ablations test dependency and cumulative-commitment checks together, leaving their individual contributions unresolved. Evidence quality and the audit mechanism itself require validation.

## Related notes

- [Agent workflow structural testing](2026-agent-workflow-structural-testing.md)
- [Three pillars of oversight](../security-governance/2026-three-pillar-agent-oversight.md)

## Free check and usage status

Proposed, untried. Give toy agents repeated, independent and contradictory statements with known sources. Record proposed and committed changes, false acceptance and false blocking. Next inspect feature grounding and calibration on held-out cases before considering a deployment.

## Primary sources

- [Versioned record](https://arxiv.org/abs/2610.38869v1)
- [Inspected full text](https://arxiv.org/html/2610.38869v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
