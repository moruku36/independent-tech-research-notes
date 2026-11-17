**English** | [日本語](2026-signed-requirement-manifest-handoffs.ja.md)

# Signed handoffs: integrity after extraction, not correctness before it

## Overview

- **What it is**: A preregistered synthetic study of requirement preservation between agents.
- **What it says**: A runtime-authenticated manifest plus executable checks reduces some unsafe decisions.
- **Caveat**: An already-corrupted extraction can receive a valid authentication tag.

## Practical reading (six lines)

- The question is whether a user's requirements survive delegation and merging.
- The system extracts quoted requirements and predicates, authenticates them, and verifies decisions in code.
- Integrity in transit does not repair a requirement corrupted before authentication.
- Proposed use: preserve trusted original requests separately from model-generated summaries.
- Test extraction fidelity, tamper rejection, decision validity, and abstention as separate stages.
- The reported decision commits are synthetic actions, not measured unsafe Git merges.

## Source and reading scope

Xiaobo Chen, Genliang Zhu, Ziyuan Wang, Chu Wang, *Signed but Not Safe: Requirement Integrity in Multi-Agent LLM Handoffs*, arXiv:2611.07483v1, 2026-11-05. Checked 2026-11-18 JST: selected HTML threat model, methods, outcome tables, pre-signing follow-up, and validity limits. Partially read; requested-only artifacts not obtained; no reproduction.

## Evidence and limitations

The trusted runtime holds the HMAC-SHA256 key outside prompts; it checks provenance and executable predicates. HMAC is shared-key authentication, not public-key signing. Compromise of the orchestrator or harness, and key theft, are outside the evaluated boundary.

The main Qwen3-8B experiment contains 1,440 trajectories. Its attacked comparison reports 69.4% to 9.0% unsafe commits; a separate pre-signing attack raises the signed arm from 14.6% to 37.5%. These use different conditions and must not be combined into one rate. Rejection/abstention contributes to safety. Small synthetic tasks and limited model subsets do not establish general protection for natural-language requirements.

## Application and free check

Proposed / untried. Build an offline fixture with a trusted original request, a manually checked manifest, and simple predicates. Change one quote, predicate, revision, or final value at a time; distinguish authentication failure, extraction mismatch, decision failure, and safe abstention. Keep keys and the acceptance policy outside candidate-controlled inputs. Then deliberately authenticate an incorrect manifest to demonstrate the pre-authentication gap. This can inspect control logic without LLM calls, but cannot reproduce model extraction quality. A later evaluation should include paraphrases, preferences versus obligations, utility loss, and a stronger independent verifier.

Usage status: proposed / untried / not adopted. No model calls, environment changes, or experiments were performed for this note.

## Related notes

- [Pre-processing safety boundary](2026-step-zero-before-observability.md)
- [Trusted verification rules](../coding-agents/2026-claude-code-verification-practices.md)

These are reading comparisons, not matched performance evaluations.

## Sources

- [Submitted paper / 指定論文](https://arxiv.org/abs/2611.07483)
- [Inspected text v1 / 確認した本文](https://arxiv.org/html/2611.07483v1)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
