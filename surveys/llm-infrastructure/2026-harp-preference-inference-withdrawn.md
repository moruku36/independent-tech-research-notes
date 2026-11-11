**English** | [日本語](2026-harp-preference-inference-withdrawn.ja.md)

# HARP preference inference — withdrawn preprint

## Overview

- **What it is** Withdrawn preprint about inferring preferences in multi-agent orchestration.
- **What it says** Earlier v1 proposes numeric beliefs over candidate preferences, updated from observed actions.
- **Caveat** The current v2 is a withdrawal notice. The authors cite confusion involving preferences, personas and the title.

## Practical reading (six lines)

- The repository records the withdrawal alongside the historical proposal.
- HARP keeps a separate posterior for each agent over fixed candidates.
- The language model supplies action likelihoods for Bayesian updates.
- The theoretical equivalence relies on stated factorization assumptions.
- A proposed toy exercise can compare a text description with an explicit probability table.
- Treating the withdrawn claims as validated findings would require fresh evidence.

## Source and reading scope

Shuqing Shi, Ziyan Wang, Milind Tambe and Yali Du. arXiv:2610.07587, v1 submitted 2026-10-06, withdrawn in v2 on 2026-10-07. Checked 2026-11-12 JST. Examined the current notice and selected method and limitation sections in v1.

## Method, evidence and limitations

The earlier method assumes a finite candidate library and a calibrated likelihood scorer. Preference drift and candidates outside the library complicate interpretation. The withdrawal reason is recorded from arXiv. A corrected successor has yet to be identified.

## Related notes

- [Recursive multi-agent systems](2026-recursive-multi-agent-systems.md)

## Free check and usage status

Proposed, untried. Use scripted toy agents with explicitly assigned choices and likelihoods to inspect posterior updates. No inference about real people is needed. Next check for a corrected paper and its relationship to the withdrawn version before using its empirical claims.

## Primary sources

- [Current record and withdrawal](https://arxiv.org/abs/2610.07587)
- [Earlier v1](https://arxiv.org/html/2610.07587v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
