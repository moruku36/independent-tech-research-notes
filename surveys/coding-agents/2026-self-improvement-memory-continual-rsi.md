**English** | [日本語](2026-self-improvement-memory-continual-rsi.ja.md)

# Self-Improvement Memory: carrying harness improvement evidence forward

## Overview

- **What it is**: A preprint about memory for harness optimization.
- **What it says**: Improvement evidence can support subsequent optimization.
- **Caveat**: Transfer does not guarantee gains.

## Practical reading

- **Question**: What should survive when a harness or its underlying model changes?
- **Approach**: SIM preserves diagnoses, edits, predictions, outcomes, and context.
- **Finding**: The paired coding study reports a benefit; see the evidence below.
- **Proposed development use**: Link each Codex harness change to a hypothesis, commit, and check result.
- **Proposed memory use**: Keep an improvement ledger separate from task notes and sleep-generated summaries.
- **Caution**: Treat retained diagnoses as hypotheses to retest, never as automatic approval for changes.

## Source and reading status

- Paper: [Self-Improvement Memory Enables Continual Recursive Self-Improvement](https://arxiv.org/abs/2611.18856), Xin Yu et al., 2026; arXiv:2611.18856v1, submitted November 13.
- Checked: 2026-11-18. Primary source partially read: [HTML](https://arxiv.org/html/2611.18856v1), §§3–4, limitations, Appendices C–D. Not reproduced; acceptance status and implementation artifacts unverified.

## Method, evidence, and limits

SIM belongs to the optimizer, with policy weights fixed. Comparisons include cold start, harness-only transfer, diagnosis-only memory, and full SIM. Held-out feedback stays outside optimization.

In ten paired Terminus-2 coding continuations, SIM wins nine; mean advantage **2.36 score points**, paired **p=0.003** (Table 3). Other main conditions have one optimization run each.

Runs match ten rounds and five proposals per round, not tokens or runtime. SIM records selected edits, including failures; full memory enters prompts without retrieval. Compatible interfaces are required. In the final generation transition, fresh optimization scores higher. Inherited memory and target updates are evaluated together. These details come from [§§3–4, limitations and Appendices C–D](https://arxiv.org/html/2611.18856v1).

## Proposed application to Codex and GitHub

**Our design interpretation; unimplemented and untested.** Start with a versioned `improvement-ledger/` directory alongside harness configuration. Give a problem a stable ID; preserve competing explanations rather than silently merging similar wording.

For each proposed edit, record the failure evidence, hypothesis, expected checks, model identifier, harness commit, evaluation-set version, observed outcome, and superseding decision. Separate “selected for evaluation” from “passed acceptance checks.” A useful record must remain interpretable after its patch is reverted.

Keep task working memory in its existing location. A sleep/consolidation step could produce candidate lessons from the ledger, each pointing back to immutable evidence. Require fresh checks before promoting a lesson into a prompt, skill, tool wrapper, or completion rule. This proposal does not establish that existing sleep implementations already provide this behavior.

## Free preliminary check plan

1. Use three to five existing, non-sensitive PRs and saved logs. Manually create ledger records, without new model calls or infrastructure.
2. Ask whether a second reader can reconstruct the prediction, actual outcome, affected revision, and unresolved question from each record.
3. Design a future comparison from identical harness commits: no ledger, diagnosis-only ledger, and evidence ledger. Freeze acceptance tasks outside the edit scope; track regressions, repeated failed fixes, success, tokens, and time.
4. First verify the recording workflow offline. A later paid benchmark would need a separate budget; this preliminary check cannot reproduce the paper's performance gain.

## Related reading

These are repository reading paths, not experimentally validated integrations:

- [Frozen-weight improvement and failure traces](2026-frozen-weight-failure-trace-lessons.md): compare what evidence is retained.
- [EvoAudit](2026-agent-evolution-evoaudit.md): plan checks for previously successful tasks.
- [Anthropic agent memory](../llm-infrastructure/2026-anthropic-agent-memory-components.md) and [OpenClaw dreaming](../llm-infrastructure/2026-openclaw-dreaming-memory-consolidation.md): consider where a separate improvement ledger would fit.
- [Claude Code verification](2026-claude-code-verification-practices.md): keep acceptance evidence independently inspectable.

## Usage status and next checks

**Proposed / untried / not adopted.** No harness code, model settings, or execution permissions changed.

Before implementation, verify artifact availability, exact environment versions, independent-run reproducibility, memory growth and cost, and whether inherited records alone help without target-time updates. Check these against the primary materials rather than assuming a production-ready package exists.
