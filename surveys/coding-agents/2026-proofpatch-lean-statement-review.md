**English** | [日本語](2026-proofpatch-lean-statement-review.ja.md)

# ProofPatch: keeping Lean statement reviews valid across revisions

## Overview

- **What it is**: A Lean review tool for checking statements and tracking when earlier review decisions remain applicable.
- **What it says**: It fingerprints elaborated statements and their dependencies, and can block a change that violates an explicit lock.
- **Caveat**: Checking a Lean proof and judging whether its statement captures the original intent require different evidence.

## Practical reading (six lines)

- The tool records what Lean interpreted, including relevant dependencies, so harmless notation changes can preserve review decisions.
- When a dependency changes, affected statements can return for review even if their source text stayed the same.
- The Mathlib study marked 118 of 12,898 synthetic review decisions for reconsideration across 229 revision pairs.
- On 1,527 labeled statements, the evidence probes reported 88–96% precision with only about 5–8% recall.
- No changed locked statement or unfinished proof was accepted in 344 agent runs in the study. This result covers the tested policy and setup.
- Proposed use: explicitly lock critical definitions as well as statements and keep a human check against the informal specification.

## Source and reading scope

Xujun Che, Depeng Xu, Jian Xiang and Taufiqua Khan, *ProofPatch: Reviewing Lean Statements and Keeping the Reviews Valid as Formalizations Evolve*, arXiv v1, October 31, 2026. Checked Sections 3–5 and 7 and Tables 1–3 on November 24, 2026 JST. No proof checking or reproduction was run for this note.

## Evidence and limitations

- **Reviews and locks.** A review record binds an elaborated statement to the transitive definitions it uses. The gate uses fingerprints and checks definitional equality for some rewrites. Statement, definition, and axiom restrictions have distinct scopes. An unchanged statement can still need review if the meaning of a referenced definition changes.
- **Evaluation.** Under the authors’ reference notion of change, the full gate sent 118 of 12,898 synthetic decisions for review with no excess or missed flags. The comparisons use 229 Mathlib revision pairs, with a synthetic review on every prior theorem. In the statement-fidelity evaluation, stricter and broader probes reach different precision and low recall. They can supply evidence of a mismatch, while the informal intent still needs review.
- **Agent runs.** The study used one open-weight model in the judge and agent experiments. Among 344 agent runs, the gate accepted no output with a changed locked statement or proof placeholder. The evidence concerns this evaluation and the declared lock scope.

## Application and free check

Proposed. Take a small own Lean specification and compare three cases on paper: a notation-only edit, a change to a referenced definition, and a proof-only refactor. Record separately which cases should preserve an approval, trigger review, or fail a lock.

## Related note

- [Formally verified quantum program discovery](2026-formally-verified-quantum-discovery.md)

## Sources

- [arXiv record](https://arxiv.org/abs/2611.01357)
- [Inspected v1 text](https://arxiv.org/html/2611.01357v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
