**English** | [日本語](2026-microsoft-perception-ignite.ja.md)

# Microsoft Perception: agentic security and evidence boundaries

## Overview

- **What it is**: Microsoft's Ignite announcement of a coordinated security-agent system.
- **What it says**: Red, blue, and green roles link assessment, investigation, and remediation under human control.
- **Caveat**: Coverage, benchmark solve rate, and safety-boundary compliance are different metrics.

## Practical reading (six lines)

- The question is how security teams coordinate analysis and remediation.
- Perception uses playbooks and specialized agents with reviewable artifacts.
- The reported 80% concerns alert coverage, not correctness.
- Proposed use: separate evidence collection, assessment, approval, and scoped remediation.
- Start with synthetic incidents and read-only artifacts before any live assessment.
- GA, preview subfeatures, and partner benchmark claims require separate checks.

## Source and reading scope

Hari Pulapaka's Microsoft Community Hub post, 2026-11-17, “What's new with Microsoft Perception at Ignite 2026.” Browser body and footnote checked 2026-11-18 JST; companion Intune announcement checked. Vendor article partially read. The linked Incalmo report could not be retrieved and was not independently checked.

## Evidence and limitations

The article announces Perception GA and describes third-party signals plus API/MCP workflow integration. Its triage-coverage figure comes from an approximately eight-million-alert Microsoft analysis and is not an individual customer's guaranteed result.

It quotes partner testing of web assessment at 31.0% solve rate versus Codex's 15.2%, with 91% boundary adherence on safety-constrained tests. These are different test metrics, not assurance of safe operation or superiority over the user's present Codex setup. The underlying protocol remains unchecked here. The companion Intune offering is public preview, not blanket GA.

## Application and free check

Proposed / untried. Build a fictional incident packet and require every finding to identify evidence, scope, uncertainty, an owner, and a reversible response proposal. Check approval and recovery on paper; do not run scans or deploy changes. A later controlled trial should measure false positives, missed incidents, boundary violations, review time, and recovery outcomes separately.

Usage status: proposed / untried / not adopted. No model calls, environment changes, or experiments were performed for this note.

## Related notes

- [Ignite overview](../articles/2026-microsoft-ignite-frontier-ecosystem.md)
- [Requirement integrity](../agent-safety/2026-signed-requirement-manifest-handoffs.md)

These are reading comparisons, not matched performance evaluations.

## Sources

- [Supplied article / 指定記事](https://techcommunity.microsoft.com/blog/perception-blog/whats-new-with-microsoft-perception-at-ignite-2026/4571834)
- [Intune public preview / Intuneのpublic preview](https://techcommunity.microsoft.com/blog/intunecustomersuccess/microsoft-perception-helps-it-drive-outcomes-and-scale/4573285)
- [Linked benchmark, uninspected / リンク先評価・未確認](https://aka.ms/incalmo)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
