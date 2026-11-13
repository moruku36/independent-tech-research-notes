**English** | [日本語](2026-collusion-probe-evaluation-pitfalls.ja.md)

# Collusion monitors: instruction exposure, decisions and timing

## Overview

- **What it is** Evaluation study of monitors for hidden collusion among language-model agents.
- **What it says** Strong probe scores can reflect exposure to a collusion instruction and outcome leakage.
- **Caveat** Synthetic tasks, noisy labels and white-box access limit deployment claims.

## Practical reading (six lines)

- The benchmark adds agents that receive a collusion instruction but decline.
- One probe’s agent AUROC falls from 1.00 to 0.61 when briefing/private context is removed.
- A decision-trained probe retains 0.73 in that test.
- A vote-only rule scores 0.990 after voting, which does not establish early detection.
- Activation probes require internal model access unavailable in closed API systems.
- Proposed application: evaluate monitors using refusers, benign coordination and strictly pre-action observations.

## Source and reading scope

Mainul Hasan Mohsin and Mohammad Shahidur Rahman, *What Do Collusion Probes Read? Three Pitfalls in Evaluating Multi-Agent Collusion Monitors*. arXiv:2611.10620v1, 2026-11-07. Checked 2026-11-14 JST, selected §§8 and 12, Table 4 and introductory timing results. Venue unconfirmed.

## Method, evidence and limitations

The suite contains 2,500 committee and 1,476 code-review episodes. Reported figures refer to specified probes and contexts, not universal monitor quality. The decision probe recalls 45% of attempts at 1% false positives in the reported committee test. Emergent collusion, adaptive training against monitors and generalization beyond two synthetic task formats remain open.

## Related notes

- [Three pillars of oversight](../security-governance/2026-three-pillar-agent-oversight.md)
- [Auditable belief updates](2026-eb-mas-auditable-beliefs.md)

## Free check and usage status

Proposed, untried. Begin with a free offline ledger separating instruction exposure, refusal, benign cooperation, decisions and observed actions. Freeze the observation cutoff before the action being predicted. Use existing synthetic records to inspect label errors, calibration and false positives before selecting a monitor. A small text-based audit is possible without activation access but cannot reproduce white-box probe results. Next inspect labels, score aggregation and model access; no probes or collusive agents were trained.

## Sources

- [Versioned record](https://arxiv.org/abs/2611.10620v1)
- [Inspected text](https://arxiv.org/html/2611.10620v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
