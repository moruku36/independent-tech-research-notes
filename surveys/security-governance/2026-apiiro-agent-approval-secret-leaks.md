**English** | [日本語](2026-apiiro-agent-approval-secret-leaks.ja.md)

# Apiiro: secret exposure through agent permission files

- Apiiro investigates public repositories where approved commands persist in settings/transcripts and expose embedded secrets.
- It reports 2,539 classified secrets across 1,994 repositories, including history and other artifacts beyond 104,185 local-settings files.
- This corporate observational study does not establish that every credential remained valid or that this user's repositories are affected.

## Practical interpretation (7 lines)

- Treat persisted approvals as potential publication artifacts.
- Excluding .env alone does not cover derived agent files.
- Examine secret interpolation and persistence as separate steps.
- Distinguish global excludes, repository settings, and already-tracked files.
- Do not assume key-pattern scanners detect ordinary password strings.
- Include settings, memory, and handoff notes in a proposed prepublication check.
- No actual secret discovery, credential testing, or settings changes were performed here.

## Metadata and verification

- Displayed title: Coding Agents Copy Your Secrets to a Hidden File. Thousands Are on GitHub; page title: Coding Agents Are Leaking Your Secrets to GitHub.
- Authors displayed: Shmulik Cohen and Matan Giladi, Apiiro.
- Published November 5, 2026; update November 8. Checked November 9 JST.
- Corporate security investigation, not a peer-reviewed paper.
- Article, methods/limits, update, and official Claude Code settings documentation reviewed. Dataset, scanner configuration, and reproduction code not independently validated.

## Method and reported evidence

The proposed leak path persists secret-bearing command strings in reusable approvals. Public GitHub searches on November 1–3 were partitioned by file size; classification used patterns, public-host context, and review.

The report identifies 1,122 current local-settings files with secrets and adds history/shared settings/transcripts to its total. Both tested scanners missed 215 files. Its “real secret” label is format/context based, not a successful authentication test.

Official settings documentation confirms approval persistence and creation-time global excludes. Ignoring files does not erase tracked history. Reported vendor investigation is not proof of a shipped remedy.

## Limitations and interpretation

Public-search coverage and selected artifacts do not estimate exposure across all developers or products. Classification error, missed cases, deduplication, and collection date matter; scanner results apply to the reported setup.

Our application is to examine persistence and publication paths, rather than prohibit all standing approvals. Applicability to the user's environment remains untested.

## Related notes

- [Claude Code publication leak paths](2026-claude-code-publication-leak-paths.md).
- [OpenClaw Dreaming](../llm-infrastructure/2026-openclaw-dreaming-memory-consolidation.md): moving logs into durable memory also raises secret-handling questions.

## Free verification proposal — not performed

Use dummy values in a disposable repository to test prepublication checks across settings, transcripts, and notes. Report paths/locations/classes without reprinting values, and distinguish tracked from untracked files. If real exposure is separately established, deletion alone does not invalidate a credential.

- Use: proposed only; no real-data audit or adoption.
- Open checks: current product remedies, detector reproducibility, and local applicability.

## Sources

- [Apiiro investigation](https://apiiro.com/blog/coding-agents-leaking-secrets-github-dont-ask-again)
- [Official Claude Code settings documentation](https://code.claude.com/docs/en/settings)
