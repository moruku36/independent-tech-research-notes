**English** | [日本語](2026-agent-iac-pull-request-study.ja.md)

# Do AI Coding Agents Write Infrastructure as Code Like Humans? An Empirical Study of GitHub Pull Requests

- This observational study separates human, bot, silent-agent, and disclosed-agent GitHub IaC contributions.
- Aggregate acceptance and within-repository comparisons produce different impressions.
- Merging is not quality; sustainability smells are not measured energy/cost, and disclosure effects are not causal.

## Practical interpretation (7 lines)

- Do not infer complete authorship from PR account names.
- Inspect repository and change-type differences before comparing merge rates.
- Review permissions, exposure, deletion, and persistent state concretely.
- Match scope and acceptance conditions and record closure reasons.
- Do not label smell detection as measured operational or environmental cost.
- Consider project-wide checks independent of authorship.
- No PR recollection, detector execution, or cloud changes were performed.

## Metadata and scope

- Authors: Amine Barrak, Emna Ksontini, Charles Wehbe.
- arXiv:2610.34613v1, October 25, 2026. Venue/peer review unconfirmed.
- Checked November 9, 2026 JST. Collection, attribution, comparison, smell analysis, and limits partially read; replication package not executed or independently inspected.

## Method and reported findings

Public PRs from January 2025–May 2026 yield 349,975 collected and 349,156 labeled PRs after 819 unreachable-commit exclusions, across 49,241 repositories. Untraced AI use can remain labeled human.

Silent agents have higher aggregate merging (87.4% versus 78.9%) but a four-point deficit within repositories. Estimates in the further screened/action-adjusted corpus use a different population.

In 2,645 matched AWS Terraform pairs, smell introduction is 10.4% versus 10.3%, paired OR 1.02, 95% interval 0.83–1.25. Lack of a detected difference does not establish quality or cost equivalence.

## Reporting caveat and limits

The abstract reports 32.9% bots, while the introduction reports 35.8%; this review does not reconcile denominators/versions and does not merge them into one estimate. Collection and labeled counts also differ.

Maintainer policy, human selection, attribution misses, LLM annotations, unavailable diffs, and public Terraform/AWS concentration constrain inference. Disclosure itself is not established as causing lower acceptance. Detector recall is unknown.

## Related notes

- [tfdrift](../cloud-resilience/2026-tfdrift-severity-taxonomy.md).
- [Incident-Arena](../cloud-resilience/2026-incident-arena-sre-reliability.md): acceptance and safe operational recovery are distinct outcomes.

## Free proposal — not performed

Manually classify a small set of publishable IaC diffs by purpose, size, permission expansion, deletion, and state handling. Review with authorship hidden and compare existing CI findings. Do not apply to infrastructure; record merging separately from technical defects.

- Use: proposed only; no reanalysis/adoption.
- Open checks: reporting discrepancy, replication artifacts, misclassification, and real operational costs.

## Primary sources

- [arXiv v1](https://arxiv.org/abs/2610.34613v1)
- [HTML](https://arxiv.org/html/2610.34613v1)
