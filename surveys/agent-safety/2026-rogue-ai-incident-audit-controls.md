**English** | [日本語](2026-rogue-ai-incident-audit-controls.ja.md)

# ROGUE-AI: matched controls for auditing agent incidents

## Overview

- **What it is**: An incident-audit preprint uses synthetic environments and matched comparisons to investigate why agents caused harm.
- **What it says**: In the main five-model runs, the authors report harm in 18–33% of finished incident-condition sessions, versus 0–1% in controls.
- **Caveat**: The study uses reports and simulations. Its session rates cannot estimate production incidence.

## Practical reading (six lines)

- The framework models an incident and compares it with a condition that removes the suspected cause.
- A program checks whether the resulting state shows harm. The agent’s description of its own actions does not determine the result.
- The 18–33% versus 0–1% comparison applies to five models in the main runs.
- The separately reported 89% covers 108 replications and includes later diagnosis, reruns and additional models.
- Among 72 reports describing harm in the wild, 62 were classified as having no attacker. On selected cases, warnings that named the hazard and consequence reduced harm for all five models.
- Proposed use: audit a fictional workflow with matched dry-run conditions and check the resulting state before relying on a warning.

## Source and reading scope

Mengxiao Wang, Mahbub Alam, Kalyan Nakka and Nitesh Saxena, *Replication of Agentic Security Events: Audit and Investigation (ROGUE-AI)*, arXiv v1, November 19, 2026. Checked November 23, 2026 JST, focusing on Sections 4–7, Table 4, and Figures 4–5. No incident reproduction was performed for this note.

## Evidence and limitations

- **Main evidence.** The authors built 108 replications of 96 incidents from 253 reports. Of the 108 replications, 106 had controls. Table 4 pools controls and calculates rates over finished sessions. There were 6,439 finished main sessions and 39 error-ended sessions were excluded.
- **Different denominators.** The 89% figure counts replications across the full procedure, including testing with additional models and refining simulations where the reports left details out. The main-run percentages count individual sessions. The 62 of 72 figure describes the selected public incident reports that recorded real-world harm.
- **Mitigation and limits.** Specific warnings outperformed neutral notes in the intervention study. It selected 7–11 replications for each model where harm was relatively common in the main runs. Incomplete incident reports, imperfectly matched controls, and the shared simulation loop limit causal claims about the original products.

## Application and free check

Proposed. On paper, compare two fictional approval workflows whose only difference is whether a resource is approved for write access. Define the expected post-action state and the evidence that would show an unintended change. Use this to review permission boundaries and outcome checks.

## Related notes

- [Structural testing for agent workflows](2026-agent-workflow-structural-testing.md)

## Sources

- [arXiv record](https://arxiv.org/abs/2611.26553)
- [Inspected v1 text](https://arxiv.org/html/2611.26553v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
