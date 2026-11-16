**English** | [日本語](2026-nemotron-for-science-release.ja.md)

# Nemotron for Science: specialized models, datasets and tool feedback

## Overview

- **What it is**: A scientific-agent bundle around Nemotron 3.5 Super VL.
- **What it says**: It combines a chemistry dataset, adaptation recipes and specialized tool workflows.
- **Caveat**: Partner results on narrow tasks do not establish discovery or clinical efficacy in general.

## Practical reading (6 lines)

- The question is how to adapt a general model to specific scientific work.
- The release combines open model/data resources and domain feedback.
- A KTH example reports 81% repair of tested GROMACS setups with independent tool checks.
- Proposed use: give each research task an executable acceptance criterion.
- Keep training data and held-out evaluation separate, and log solver failures.
- No model, training job or laboratory experiment was run for this note.

## Source and reading scope

NVIDIA, *NVIDIA Introduces Nemotron for Science to Accelerate Discoveries With Agents*, November 16, 2026. Corporate press release.

Primary release, named case studies and availability checked in the rendered page November 17, 2026. Linked technical blog, dataset splits, licenses and model artifacts not audited; no execution.

- [Submitted source](https://nvidianews.nvidia.com/news/nvidia-introduces-nemotron-for-science-to-accelerate-discoveries-with-agents)


## Method, evidence and limitations

LitmusBench v0.2 has nearly 50,000 chemistry questions for training/evaluation. Other examples cover reaction extraction and protocol design. The GROMACS result is a repair-task outcome; the release does not supply a full denominator and confidence analysis. Solver acceptance alone is not experimental validation.

## Related reading and comparison

The [MIT course note](2026-mit-htmaa-agentic-engineering-resources.md) likewise separates model proposals from tool checks. Connect this to the existing [AI Scientist note](../coding-agents/2024-sakana-ai-scientist.md) as a research-loop question, without inferring matched performance.

## Free-to-run check and usage status

Proposed, free and unrun: define a tiny offline parser/checker task with valid and invalid scientific configuration fixtures. Verify units, required fields and exit status before interpreting a natural-language success claim. This checks the harness contract, not Nemotron accuracy. Actual training or inference requires separate resource planning.

Usage status: proposed / untrialed / not adopted. No reproduction of the reported results is claimed.

## Unconfirmed points and next checks

Next: inspect the model license, dataset contamination controls, exact test cases and independent checking code before adopting a recipe.

[Category index](README.md) | [Reading list](../../docs/reading-list.md)
