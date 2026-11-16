**English** | [日本語](2026-criticality-aware-ran-placement.ja.md)

# Criticality-aware RAN placement: dependencies and failure impact

## Overview

- **What it is**: A networking preprint on placing disaggregated radio-access functions.
- **What it says**: Limiting dependencies and site criticality improves simulated disruption tolerance.
- **Caveat**: This is a topology-based simulation; the cost discussion contains inconsistent statements.

## Practical reading (7 lines)

- The question is how much service depends on each placement location.
- The model jointly optimizes dependency and placement cost with compute/transport constraints.
- A 50-RU topology is tested against random and centrality-ordered site disruptions.
- The paper reports up to 75% more operational RUs than Reveal under targeted disruptions.
- Proposed use: map required dependencies and measure each site's service impact before consolidation.
- A dependency required for operation is different from an optional replica providing redundancy.
- Do not transfer the reported gain or the unresolved cost comparison to a general cloud deployment.

## Bibliography and reading scope

Gabriel M. Almeida, Joao F. Santos, Walid Saad, Nicola Marchetti, Kleber V. Cardoso. *Criticality-Aware RAN Function Placement for Robust 6G Networks*. arXiv:2611.14121v1, 2026-11-10.

Checked 2026-11-17 JST. Primary HTML §§III–V and conclusion checked. Partial reading / not reproduced. Preprint submitted for possible IEEE publication; acceptance not independently confirmed. Plot values were not independently digitized.

- [arXiv record and version history](https://arxiv.org/abs/2611.14121v1)
- [Inspected full text](https://arxiv.org/html/2611.14121v1)
- [DOI](https://doi.org/10.48550/arXiv.2611.14121)

## Method, evidence and limitations

Evaluation uses CPLEX, a seven-day demand profile, 100 random failure realizations, and D-RAN, PlaceRAN and Reveal baselines. Criticality is capped at 0.1. The '75%' is the authors' comparison, not 75 percentage points or a universal availability gain. §V-D says 10.7% more active sites than Reveal, then says fewer; the numeric cost claim needs clarification. Transport failures and recovery are future work.

## Comparison with related notes

[SequenceFI](2026-sequencefi.md) concerns failure injection timing. This placement study instead asks which mandatory dependency makes a disruption propagate. These are complementary design and validation stages, not comparable benchmarks.

## Free-to-run check and usage status

Proposed, free and unrun: enumerate small synthetic placement graphs in plain Python, removing each mock site in turn. Count surviving end-to-end chains, maximum affected fraction, active sites and feasible placements separately. Hold resources and demand fixed; distinguish required chains from redundant alternatives. This would validate the accounting only, not reproduce CPLEX or the paper's gains. Next resolve the cost contradiction and inspect topology/data availability and sensitivity to the criticality threshold.

Usage status: proposed / untrialed / not adopted.

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
