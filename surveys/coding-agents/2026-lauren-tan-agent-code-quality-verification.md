**English** | [日本語](2026-lauren-tan-agent-code-quality-verification.ja.md)

# All Code Is Slop: executable constraints and verification for coding agents

## Overview

- **What it is**: Lauren Tan's practitioner talk at AI Engineer CODE 2026 about agent-assisted software quality.
- **What it says**: Invest in code design, executable checks and verification before scaling automation.
- **Caveat**: Reported team outcomes are self-reported; the transcript has recognition errors and no causal evaluation.

## Practical reading (7 lines)

- The question is how to increase coding throughput while retaining quality.
- Tan places architecture and static checks ahead of runtime/formal verification and judgment-based prose.
- Examples include restricted APIs, enforced Electron process boundaries and user-facing feature maps.
- She reports about 11,000 team PRs in a month and a relative revert rate near 0.5%.
- Proposed use: convert a recurring correction into a testable constraint and remove obsolete examples.
- Proposed review: inspect behavior evidence alongside the diff, with an explicit acceptance condition.
- PR count and revert rate do not establish maintainability, defect absence or safe universal auto-merge.

## Bibliography and reading scope

Lauren Tan, *All Code Is Slop (Except Mine)*, AI Engineer CODE 2026, main stage, 2026-11-11. Practitioner conference presentation, not a research paper.

Checked 2026-11-17 JST. Primary source checked / partially read / not reproduced: the organizer's reading edition and timestamped machine transcript, including design, verification and outcome passages. Direct YouTube body retrieval failed; the video/audio and every slide were not independently inspected. Upload date is unconfirmed here.

- [Requested recording](https://www.youtube.com/watch?v=O_zcc6Xl12g)
- [Organizer's page and full transcript](https://ai.engineer/code/2026/talks/lauren-tan)
- [Organizer's transcript download](https://ai.engineer/api/code/reading-download/transcripts/lauren-tan.md)

Transcript timestamps use the Day 1 livestream clock, **not** the requested clip's clock: 01:03:27 constraints; 01:06:24 Dune examples; 01:11:04 verification; 01:14:56 outcomes; 01:16:35 automation ordering.

## Evidence, interpretation and limits

The talk illustrates one team's engineering process, without a matched control or independently audited PR/incident records. Revert definitions, observation windows and selection effects remain unresolved. API/comment restrictions describe local choices, not general bans. Formal methods cover stated properties and their models; treating them as complete implementation assurance would exceed this evidence.

## Supporting primary resources

Selected current README sections were checked separately; they establish documented tool purposes, not the team's measured results or historical configuration:

- [pstack README](https://github.com/cursor/plugins/blob/b4a4f6151b8e77f8d71045f09f553a733cf0ed37/pstack/README.md): lists project verification with feature maps and a statechart skill.
- [Bombadil README](https://github.com/antithesishq/bombadil/blob/d220fcf64825c26e0a0c72880a4f3c367be916f9/README.md): describes property-based exploration for web and terminal UIs.

Neither tool was installed, executed or audited. Their current documentation does not prove compatibility with this Codex environment.

## Related reading

[SlopCodeBench](2026-slopcodebench.md) separates functional correctness from structural quality across iterative development. [Software systemic decay](2026-software-systemic-decay-essay.md) asks about overall coherence. My proposed synthesis: evaluate whether checks preserve important structure and user-visible behavior, instead of using merge volume as a substitute for those outcomes. These sources do not measure the same tasks.

## Free-to-run check and usage status

Proposed, free and unrun: use an isolated two-module toy repository with an explicit import boundary and a tiny user flow. Prepare a valid change, a forbidden dependency, and a behavior regression that still compiles. Check that the boundary validator and behavior test reject the relevant cases while retaining the valid change. Record false positives, missed failures and review effort. This would validate a checker design, not reproduce team productivity.

For a later Codex/GitHub trial, propose one versioned acceptance command, preserved logs tied to the commit, and a short feature map. Keep permission to merge and the validity of evidence as separate decisions. Next confirm checker coverage, exemptions, artifact provenance and independent acceptance criteria before adopting changes.

Usage status: proposed / untrialed / not adopted. No plugin, agent setting, CI configuration or merge policy was changed.

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
