**English** | [日本語](2026-qwen4-max-release.ja.md)

# Qwen4-Max: release claims, agent workflows and evidence

## Overview

- **What it is**: A vendor launch of Qwen4-Max for multimodal, long-running work.
- **What it says**: It combines a 2.4T backbone, native vision and a 1M-token window with delivery examples.
- **Caveat**: Provider evaluations and selected demonstrations do not establish general reliability or scientific validity.

## Practical reading (6 lines)

- The question is whether a model can deliver useful artifacts over long workflows.
- The release combines architecture changes, tool use and iterative delivery.
- Its reported Work360 score rises from 47.74 to 52.69; these are provider scores.
- Proposed use: define a reviewable first artifact and acceptance tests before a long run.
- Track corrections, tool failures, cost and completion under a fixed workload.
- The open plugin and planned smaller open models do not mean Max weights are released.

## Source and reading scope

Qwen Team, *Qwen4-Max: Your New Teammate Has Arrived*, November 16, 2026. Official release article.

Primary article, architecture, examples, safety and footnotes checked November 17, 2026 in the rendered page. Charts were not independently recomputed. No API call or benchmark reproduction.

- [Submitted source](https://qwen.ai/blog?id=qwen4-max)


## Method, evidence and limitations

The activated count is 71B, distinct from the backbone and additional N-gram embedding parameters. Live Delivery emphasizes staged review. Wet-lab coolant and computational drug-design examples have different validation levels; computational affinity is not clinical efficacy.

## Related reading and comparison

The [Preview documentation](2026-qwen4-max-preview.md) records a historical access plan; this release does not by itself settle Preview migration or compatibility. Read with [WorkflowArena](../llm-infrastructure/2026-workflowarena-executable-orchestration.md) for the distinction between model capability and executed workflow.

## Free-to-run check and usage status

Proposed, free and unrun: prepare a benign spreadsheet/report fixture with known answers and staged acceptance checks. Audit its source links and whether an early error remains in later revisions, without calling a model. Future paid comparisons need a separate budget and pinned settings.

Usage status: proposed / untrialed / not adopted. No reproduction of the reported results is claimed.

## Unconfirmed points and next checks

Next: verify current API identifiers, licenses, benchmark splits and harness settings. Do not transfer selected clinical, manufacturing or research demonstrations directly into unattended use.

[Category index](README.md) | [Reading list](../../docs/reading-list.md)
