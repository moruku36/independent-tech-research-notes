**English** | [日本語](2026-claude-code-verification-practices.ja.md)

# Claude Code verification: trustworthy checks and execution evidence

## Overview

- **What it is**: Addy Osmani's engineering account of Claude Code verification practices.
- **What it says**: Behavior checks and protected review rules support evidence-based delegation.
- **Caveat**: Team practices and self-reported outcomes are not a controlled causal study.

## Practical reading (six lines)

- The question is how an agent demonstrates that a change actually works.
- The article discusses end-to-end, property, and differential testing.
- Review rules should come from a trusted revision, not the patch being assessed.
- Proposed use: define the user-visible acceptance condition before implementation.
- Measure verifier misses and false alarms using historical failures and clean controls.
- The described commit gate has exceptions; it is not an unconditional fail-closed guarantee.

## Source and reading scope

Addy Osmani, “How the Claude Code team thinks about verification,” claude.dev, 2026-11-16. Checked 2026-11-18 JST: article body and official Code Review customization documentation. Primary engineering account and selected docs read; internal data and implementations not independently audited.

## Evidence and limitations

The account combines real application runs with diff-triggered reliability checks and incident-based verifier evaluation. It describes observation before enforcement and a repeated-block escape, so a logged verification action must not be mistaken for a passing, mandatory gate.

The official documentation confirms that the Code Review service takes REVIEW.md from a base/default branch, subject to protection-dependent behavior. It also distinguishes that service from the local /code-review command, which reads CLAUDE.md rather than REVIEW.md. Configuration must match the actual review product.

## Application and free check

Proposed / untried. Select one past bug, one clean change, and one intentional behavioral change in a local toy project. Define a fast behavior check, a relevant invariant, and an old/new comparison where appropriate. Store expected outcomes outside the candidate patch and bind results to its commit. Track false positives, missed failures, runtime, exceptions, and actual evidence. Avoid deleting a failing test merely to obtain a pass; any retirement should preserve its rationale and replacement coverage.

Usage status: proposed / untried / not adopted. No model calls, environment changes, or experiments were performed for this note.

## Related notes

- [Lauren Tan's verification talk](2026-lauren-tan-agent-code-quality-verification.md)
- [Harness benchmark](2026-frontierharness-eval-v1-1.md)

These are reading comparisons, not matched performance evaluations.

## Sources

- [Supplied engineering article / 指定記事](https://claude.dev/blog/how-the-claude-code-team-thinks-about-verification/)
- [Official Code Review configuration / 公式レビュー仕様](https://code.claude.com/docs/en/code-review-customize)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
