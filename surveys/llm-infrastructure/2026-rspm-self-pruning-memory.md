**English** | [日本語](2026-rspm-self-pruning-memory.ja.md)

# Let Them Sleep: RSPM and the risk of excessive pruning

## Overview

- **What it is**: A memory method consolidates failures into reusable rules.
- **What it says**: Reports improvements across three settings with smaller stores.
- **Caveat**: Over-pruning can discard useful history and worsen answers.

## Practical reading (six lines)

- More stored experience is not automatically better memory.
- Sleep groups failures and replaces episodes with rules.
- Software results use simulation, not live issue repair.
- Our proposal: archive originals outside active retrieval.
- Free check: test synthetic corrections and historical questions.
- A memory associated with failure may not have caused it.

## Bibliography and verification scope

Kargi Chauhan, Sadiba Nusrat Nur, Pratibha Revankar, Kyle Montgomery and Chenguang Wang; arXiv:2610.25561v1, 2026-10-18. Baylearn oral claim appears in arXiv comments, not independently confirmed.

Checked 2026-11-10 JST. Primary HTML §§1–4 and abstract metadata checked; implementation, raw data and statistical reanalysis not checked.
Status: primary source checked / partially read / not reproduced.

## Question, method, claims and evidence

The body reports an adverse LoCoMo case and historical-query harm. Its HTML abstract counts 19,008 issues while arXiv's abstract explicitly describes simulation; these are not verified real coding runs. Oracle and learned conflict handling also use different retention behavior.

## Comparison with related work

Compare an empirical memory proposal with OpenClaw's product design; neither establishes benefits in this user's agents. [Related note](2026-openclaw-dreaming-memory-consolidation.md)

## Free check plan, usage status and next checks

For agent-sleep-lab, propose reversible active-memory pruning with evidence provenance and held-out historical questions. This is our adaptation, not the paper's deletion policy. Free check: hand-label synthetic stale versus still-useful entries; do not delete real memory. Proposed only. Next: inspect simulation calibration, released code and full cost.

## Primary sources

- [Requested source](https://arxiv.org/abs/2610.25561)
- [Inspected version](https://arxiv.org/html/2610.25561v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
