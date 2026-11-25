**English** | [日本語](2026-security-prompts-ai-generated-web-apps.ja.md)

# Security prompts and scanner findings in 400 generated web apps

## Overview

- A controlled preprint on appending a security requirements block to AI coding prompts.
- Across 400 generated applications, the security prompt reduced the estimated scanner finding count by 35%, and declared dependencies expanded.
- Findings come from specific automated tools. The experiment measures the combined instruction and generated dependency changes.

## Six practical takeaways

- The study generated 400 applications from 100 fixed specifications, two coding tools and two prompt variants.
- The added OWASP-aligned security requirements corresponded to 35% fewer reported findings per generated app after adjustment (IRR 0.65, 95% CI 0.60–0.71).
- High-severity first-party source findings fell by nearly half. Added dependencies increased the absolute number of high-severity dependency advisories.
- Declared direct dependencies roughly doubled in the Node.js slice, and counts normalized by declared dependencies did not rise.
- The report combines scanner output without comprehensive manual adjudication. The tested tools, specs and scanners delimit the result.
- Proposed use. Pair secure requirements with explicit review of new dependencies and independently inspect high-severity findings.

## Publication and review scope

Darko Andročec, arXiv:2611.28408v1, submitted November 20, 2026. Reviewed the abstract and PDF results and limitations on November 26, 2026 JST. No reproduction.

## Evidence and limitations

- Each fixed spec was realized once per tool and prompt variant. The aggregate incidence-rate ratio is adjusted for the tool, complexity tier and language. A repeated generation study would help assess variability.
- The per-app advisory count reflects how many dependencies an app declares. The dependency-normalized and first-party figures answer different questions, so track each separately.
- Adding requirements can change functionality, package choices, and scan visibility at once. The tested design cannot isolate the contribution of instruction wording to each outcome.

## Application and low-cost check

Proposed and untried. Review a small set of generated apps you control using existing defensive scanners. Compare first-party and dependency findings, log new packages and manually review a sample of alerts with application owners.

## Related notes

- [Claude Code verification practices](2026-claude-code-verification-practices.md)
- [Enterprise coding-agent security](../security-governance/2026-anthropic-enterprise-coding-agent-security.md)

## Sources

- [arXiv v1 abstract](https://arxiv.org/abs/2611.28408v1)
- [Preprint PDF, experiment and results](https://arxiv.org/pdf/2611.28408)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
