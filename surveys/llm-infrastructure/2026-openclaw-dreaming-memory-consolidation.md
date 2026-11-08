**English** | [日本語](2026-openclaw-dreaming-memory-consolidation.ja.md)

# OpenClaw Dreaming: evidence-backed external-memory consolidation

- This official product document describes consolidating daily experience into durable external memory.
- Light, REM, and Deep stages prepare, select, validate, and record grounded memory updates.
- External-memory editing is distinct from weight training; implementation descriptions do not demonstrate performance gains or secret protection.

## Practical interpretation (7 lines)

- Separate collection, reflection, and durable promotion.
- Avoid recycling generated reflections as new evidence.
- Preserve provenance, observation time, and supersession relationships.
- Keep preimages and diffs for investigation and recovery.
- Examine secret-bearing logs separately from memory-quality validation.
- Compare frozen pre/post-consolidation snapshots against retrieval alone, including total costs.
- This review changed no OpenClaw settings, schedules, or model execution.

## Metadata and scope

- Original title: Dreaming. Publisher: OpenClaw documentation.
- Type: mutable product/operations documentation, not a paper; publication date and fixed software version not established.
- Checked November 9, 2026 JST.
- Main sections reviewed: phases, ingestion, safety, diary, settings/CLI, and plugin boundaries. Source code, installed version, and runtime behavior unverified.

## Mechanism and evidence

The documented pipeline stages candidates in Light/REM and promotes to MEMORY.md in Deep after threshold checks and source revalidation. SQLite retains rewrite preimages; DREAMS.md is a human-readable diary excluded from promotion sources.

Consolidation filters untrusted/system provenance, validates structured decisions and source references, and bounds prior-entry loss and context size. Transcript ingestion explicitly does not mask secrets first. The documented default is enabled, but selected memory plugins and installed versions affect applicability.

## Limits and proposed interpretation

No comparative benchmark or improvement in this user's environment is established. Provenance filtering does not itself prove truth, redact secrets, or detect every malicious instruction. Documented defaults are not observations of an installed system.

For our proposed harness, candidates, evidence, prior snapshots, diffs, and rejection reasons are useful design elements. This reading task does not modify agent-sleep-lab or any running installation.

## Related notes

- [Anthropic external memory](2026-anthropic-agent-memory-components.md).
- [Google Sleep](2026-google-sleep-continual-learning.md): a different intervention involving weights.
- [Apiiro exposure report](../security-governance/2026-apiiro-agent-approval-secret-leaks.md): memory and transcripts can carry secrets too.

## Free/low-cost verification proposal — not performed

Use synthetic logs with corrections, duplicates, stale facts, and hostile instructions. Trace candidate and promotion decisions manually. Compare original-log retrieval with consolidated memory on separate questions, measuring traceability, omissions, preparation, and answering costs. Separate preview from writes before considering real-data ingestion.

- Use: proposed only; no implementation or reproduction.
- Open checks: installed behavior, rollback, redaction, and project boundaries.

## Primary source

- [OpenClaw Dreaming](https://docs.openclaw.ai/concepts/dreaming)
