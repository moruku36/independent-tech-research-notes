**English** | [日本語](2026-openai-perplexity-intelligence.ja.md)

# Perplexity and intelligence: pretraining measurement and safety proposals

## Overview

- **What it is**: OpenAI Chief Scientist Jakub Pachocki argues for monitoring pretraining via log-perplexity and using comparable measurements in safety discussions.
- **What it says**: The essay gives historical values from a fixed snapshot of internal held-out code and proposes shared development limits linked to concrete monitoring milestones.
- **Caveat**: The internal series does not establish universal capability thresholds or supply a shared dataset for comparing labs.

## Practical reading (six lines)

- Log-perplexity is cross-entropy loss here. Lower values indicate better token prediction on the same evaluation setup.
- The essay reports approximately 0.99 for GPT-3.5 and 0.91 for GPT-4 on a fixed snapshot of internal held-out code.
- It associates about 0.76 with progress on open math problems in OpenAI’s evaluation experience.
- The suggested 0.68–0.70 range is an extrapolation. No specific new capability or validated trigger is established for that range.
- The author proposes shared limits tied to concrete advances in how models are measured and monitored.
- Proposed use: record next-token prediction loss alongside task results and safety evidence, with the evaluation conditions attached.

## Source and reading scope

Jakub Pachocki, OpenAI, November 22, 2026. Checked the essay and its dataset and attribution footnotes on November 23, 2026 JST. The underlying internal snapshot, evaluation runs, and cross-lab comparisons were not independently checked.

## Evidence and limitations

- **Measurement.** The reported numbers are the logarithm of perplexity, on the organization’s fixed held-out code snapshot. The author points out that different labs use different data and that a code-only view can be a poor proxy for older models. Keep the corpus, tokenization, measurement units, and evaluation procedure explicit when comparing results.
- **Interpretation.** Historical examples connect lower loss with capabilities observed after training. The essay notes that changes outside pretraining, including elicited reasoning, can improve downstream capabilities while leaving the reported base-model loss unchanged. The forecast around 0.68–0.70 is the author’s expectation, and the causal effect of crossing a numeric boundary has not been established.
- **Governance proposal.** Pachocki proposes industry transparency and common development limits linked to concrete monitoring milestones, alongside other measures. The essay attributes most of OpenAI’s 2026 acceleration in the loss plot to long-term research and compute investment, with automation a smaller contributor. The proposal does not constitute an adopted standard.

## Application and free check

Proposed. Make a local measurement sheet using a public corpus and a fixed evaluation procedure. Record loss, task success, and monitor performance as separate columns, and write down what evidence would justify changing a decision threshold.

## Related notes

- [Research acceleration and the jagged frontier](2026-openai-research-acceleration-jagged-frontier.md)
- [OpenAI’s frontier risk controls](../agent-safety/2026-openai-frontier-risk-model-lifecycle.md)

## Sources

- [OpenAI essay](https://openai.com/index/perplexity-and-intelligence/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
