**English** | [日本語](2026-self-organized-agent-improvement-gameplay.ja.md)

# Self-organized agent improvement through gameplay and text context

## Overview

- **What it is** A preprint on self-organized learning in controlled games.
- **What it says** A teacher revises text read by a fresh player whose weights stay fixed.
- **Caveat** The experiment covers short game horizons and finite revision budgets.

## Practical reading (six lines)

- The teacher can generate games, observe play, and revise the player's files.
- The main setup compares six models, with three teacher runs per model.
- The canonical limits are 20 text edits and 150 observed plays.
- Fresh players use the before and after contexts on held-out games at fixed budgets.
- Some text transfers to longer games, other engines, and another model.
- An internal trial could use held-out tasks and versioned guidance under fixed budgets.

## Source and reading scope

Shobhita Sundaram, Cansu Sancaktar, and Phillip Isola, arXiv:2611.23219v1, November 17, 2026. Read §§3–5 and 7 in part on November 19, 2026 JST.

## Evidence and limitations

In PuzzleScript-t20, Opus 5 went from 25.4% without an artifact to 47.5% using Astra's artifact. Astra went from 67.1% to 72.1% using Opus's artifact. Table 1 reports means and standard deviations over three seeds. Tighter exposure to the t20 budget helped t20 and reduced t30 transfer. The authors report diminishing returns and leave causal attribution and open-ended domains unresolved.

## Application and free check

Proposed and untried. Prepare a small offline evaluation table with a fixed task budget, a frozen set of holdout cases, and baseline and revised guidance versions. Keep the holdout results out of the revision process.

Usage status is proposed. This reading note did not include deployment or independent reproduction.

## Related note

- [Related repository note](2026-self-improvement-memory-continual-rsi.md)

## Sources

- [Primary report, arXiv v1](https://arxiv.org/html/2611.23219v1)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
