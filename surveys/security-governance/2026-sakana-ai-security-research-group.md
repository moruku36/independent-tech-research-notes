**English** | [日本語](2026-sakana-ai-security-research-group.ja.md)

# Sakana AI’s Security Research Group: prevention and collective defense

## Overview

- **What it is**: Sakana AI’s announcement of a public-interest security R&D group that operates separately from its commercial work.
- **What it says**: The group proposes prevention through design, coordinated defense across organizations, and safeguards for AI systems and the agents that defend them.
- **Caveat**: The announcement sets a research agenda. It cites previous research and public statistics, while the impact of the proposed cross-organization defense remains to be measured.

## Practical reading (six lines)

- The group treats security as a quality requirement to define during design and check throughout operation.
- It proposes testing automated fixes against criteria outside the proposing agent’s control and preparing a way to roll them back.
- Coordinated defense across organizations raises open questions about consent, trusted provenance, and accountability when a shared signal leads to action.
- Its AI security agenda starts with limiting defensive agents’ authority and recording why they acted.
- IPA recorded 20,073 Japanese-language JVN iPedia entries in Q3 2026, up from 10,869 a year earlier. Of the new quarter’s entries, 19,913 came from the US NVD.
- Proposed use: pick one service and document its security requirements, independent verification, approval owner, and rollback criteria before allowing automated changes.

## Source and reading scope

Sakana AI, November 20, 2026. Checked the English and Japanese announcement and relevant IPA, NIST, and Japanese financial-sector publications on November 22, 2026 JST. No benchmark was rerun and no defensive agent or production system was tested.

## Evidence and limitations

- **Research agenda.** The group plans work across product quality, system design and configuration, operations and patching, and detection and response. Its long-term emphasis is the first two. The organization links this approach to the Kano model’s idea of a basic quality expectation. It plans to publish papers, reproducible benchmarks and practical guidance, with coordinated disclosure for vulnerabilities. Detailed publication policy remains under development.
- **Operational evidence.** IPA’s counts are database registrations based primarily on imported US NVD records. NIST separately reports a 263% increase in CVE submissions from 2020 to 2025 and a move to risk-based enrichment. Its operational notice distinguishes inclusion in the database from the addition of analysis. These series have different counting rules and time windows, and neither attributes a quantified share of the growth to AI.
- **Deployment questions.** The announcement cites earlier Sakana AI research and benchmark results. Those examples motivate the agenda, which leaves field effectiveness, coordination costs, and accountability unresolved. The Japanese financial-sector guidance discusses patching responsibilities and service-level agreements with vendors. Its documented scope is financial institutions and related entities.

## Application and free check

Proposed. Use a fictional service and maintenance provider to make a one-page record of security requirements, who can verify and approve a change, how to roll it back, and what information can be shared. Evaluate whether another person could review the decision from the record alone.

## Related note

- [LLM vulnerability research and public disclosure evidence](2026-sok-llm-vulnerability-evidence.md) reviews dated capability reports and the limits of attributing disclosure trends.

## Sources

- [Sakana AI announcement](https://sakana.ai/security-research-group/)
- [IPA’s JVN iPedia Q3 2026 registration report](https://www.ipa.go.jp/security/reports/vuln/jvn/ipedia2026q3.html)
- [NIST’s NVD prioritization notice](https://www.nist.gov/news-events/news/2026/04/nist-updates-nvd-operations-address-record-cve-growth)
- [Japanese financial-sector response guidance](https://www.fsa.go.jp/news/r7/sonota/20260522-5/01.pdf)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
