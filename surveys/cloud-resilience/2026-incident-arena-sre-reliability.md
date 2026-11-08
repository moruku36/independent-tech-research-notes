**English** | [日本語](2026-incident-arena-sre-reliability.ja.md)

# Incident-Arena: Getting agents to the last nine of reliability

- This preprint benchmarks incident repair in running Kubernetes applications.
- Twenty tasks check recovery together with persistence, data preservation, and permitted change scope.
- It does not certify production reliability; few repetitions, substrate imbalance, and reporting discrepancies limit interpretation.

## Practical interpretation (7 lines)

- Separate plausible diagnosis/patches from operational recovery.
- Consider observation under load rather than alert disappearance alone.
- Check restart persistence and data integrity separately.
- Evaluate unnecessary post-fix changes and premature completion.
- Calibrate a verifier with both a golden fix and a no-op.
- Measure reasoning budget, repair success, and total cost separately.
- No cluster, fault injection, or external-service operation was performed here.

## Metadata and scope

- Authors: Andre Fu, Malik Drabla, Leon Liu, Meji Abidoye, Marek Šuppa, Lata Mishra, Adnan El Assadi, Yiyuan Li.
- arXiv:2610.00648v1, September 30, 2026. Do not infer submission date from ID alone. Venue/peer review unconfirmed.
- Checked November 9, 2026 JST. Abstract and main HTML construction, verifier, experiment, results, and limitations partially read; code/images/all appendices not independently validated.

## Method and evidence

Twenty tasks use ephemeral Kubernetes environments and three substrates: Saleor, FrappeERP, and a custom Slack-like system. Ten configurations, available reasoning levels, and three repetitions produce 3,000 trials.

Final pass/fail uses LLM-free Outcome and Safety gates with load, restart, and state checks. Post-hoc reward-hacking classification uses LLM judges, a separate process.

## Discrepancies and limits

The arXiv abstract reports 2.81M tokens/41 turns; HTML reports 4.0M/68 steps. Best performance is described as 64.3% in one place and 65% in the conclusion. Calculation/version differences remain unresolved here; do not combine them into precise costs or rankings.

Intervals are wide with three repetitions, and 13 tasks use the Slack-like substrate. Models, native harnesses, faults, and access surfaces confound comparisons. Post-fix behavior associations do not establish universal causal effects. “Last nine” is not an achieved production-availability guarantee.

## Related notes and application

- [Kubernetes agent containment](../security-governance/2026-kubernetes-autonomous-agent-containment.md).
- [AI IaC PR study](../coding-agents/2026-agent-iac-pull-request-study.md): merging differs from operational quality.

For our agents, a proposed completion contract separates stable observations, preserved state, and permitted scope from code changes. Fix targets and recovery procedures before testing; do not assume live production experimentation.

## Low-cost proposal — not performed

Use a small local mock service with misconfiguration and a restart-volatile workaround. Manually compare healthy, no-op, persistent-fix, and temporary-fix outcomes. This is not full benchmark reproduction. Cloud/model expenses are separate and none were incurred for this proposal.

- Use: proposed only; no implementation/reproduction.
- Open checks: numerical discrepancies, artifacts, verifier conditions, and total setup/evaluation cost.

## Primary sources

- [arXiv v1](https://arxiv.org/abs/2610.00648v1)
- [HTML](https://arxiv.org/html/2610.00648v1)
