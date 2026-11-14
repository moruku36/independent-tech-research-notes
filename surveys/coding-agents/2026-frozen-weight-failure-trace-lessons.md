**English** | [日本語](2026-frozen-weight-failure-trace-lessons.ja.md)

# Frozen-weight self-improvement: what failure traces add

## Overview

- **What it is** Controlled study of notes that improve a frozen-weight agent.
- **What it says** Failure-informed notes add 4.0 percentage points over matched search on generated decisions.
- **Caveat** Full conversations and held-out tool-use tasks show no demonstrated gain; small effects remain possible.

## Practical reading (six lines)

- The executor is Qwen3.5-9B with thinking off; a larger teacher writes notes.
- A matched search withholds episodes while retaining the writing and selection process.
- That search accounts for about 60% of total decision-level improvement.
- Both retail writers already know the target rules, so this is not rule discovery.
- A blind audit labels 146 of 240 held-out BFCL items defective.
- Proposed application: compare failure lessons with matched search, neutral notes and fresh held-out tasks.

## Source and reading scope

Arkid Mitra and Snehil Saluja, Agent Self-Improvement with Frozen Weights: The Added Value and Limits of Failure Traces. arXiv:2611.11342v2, 2026-11-11; first posted 2026-11-08. Checked 2026-11-15 JST, selected §§2–4. Earlier-version differences and venue unconfirmed.

## Evidence and limitations

The +4.0-point estimate is below the registered five-point worthwhile threshold. Passing a selection gate did not certify transfer. The neutral-note advantage is exploratory; scorer audits and intervals constrain interpretation. One model and two benchmarks limit generalization.

## Related notes

- [CAMP-II memory training](2026-camp-ii-file-memory-distillation.md)
- [Darwin Gödel Machine](2025-sakana-darwin-godel-machine.md)

## Free check and usage status

Proposed, untried. First make a free offline evaluation ledger with frozen tasks, scorer checks, note provenance and costs. A later local trial should hold writer, search rounds and selection budget constant across failure-informed and no-trace arms, add a neutral note, and evaluate fresh task families. Next inspect randomization, defective-item rules and replication artifacts before adopting lessons. No training or agent experiments were run.

## Sources

- [Submitted source](https://arxiv.org/abs/2611.11342v2)
- [Inspected text](https://arxiv.org/html/2611.11342v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
