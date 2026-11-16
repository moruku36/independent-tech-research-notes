**English** | [日本語](2024-refusal-single-direction.ja.md)

# Refusal as a model-specific direction: evidence and limits

## Overview

- **What it is**: A mechanistic study of refusal in 13 open chat models.
- **What it says**: Suppressing the direction reduces refusal; adding it can induce refusal of benign inputs.
- **Caveat**: The finding is neither a universal safety switch nor evidence about current closed models.

## Practical reading (7 lines)

- The question is which internal representation causally mediates refusal.
- The study contrasts benign and harmful inputs and intervenes on activations.
- A direction is found separately for each model; it is not a single neuron.
- Proposed use: measure refusal, output harmfulness and legitimate task completion separately.
- Keep authorization and tool permissions explicit outside the model as an independent control.
- Retain benign-task tests so a defensive change does not silently increase over-refusal.
- These are untested design proposals; the paper does not validate a complete agent security boundary.

## Source and reading scope

Andy Arditi, Oscar Obeso, Aaquib Syed, Daniel Paleka, Nina Panickssery, Wes Gurnee and Neel Nanda. *Refusal in Language Models Is Mediated by a Single Direction* (2024). arXiv:2406.11717v3; [DOI](https://doi.org/10.48550/arXiv.2406.11717).

Checked November 16, 2026. First submitted June 17, 2024; v3 October 30, 2024. Primary HTML §§2–7 checked; appendices and code not exhaustively audited. Primary source checked / not reproduced. Venue not independently verified.

- [Requested full-text version](https://arxiv.org/html/2406.11717v3)
- [Versioned abstract and history](https://arxiv.org/abs/2406.11717v3)

## Method, evidence and limitations

Models span 1.8–72B. Refusal string matching and Llama Guard 2 harmfulness classification are separate measures (§2.5). General benchmarks mostly persist, but TruthfulQA declines (§4.3). System prompts matter; suffix analysis covers one model and one example. Direction semantics remain uncertain (§7).

## Related reading and comparison

The comparison here is about evaluation layers, not matched performance: [Ignored, Not Refused](2026-ignored-not-refused-prompt-injection.md) distinguishes attack failure from task completion, while [AgentCap](2026-agentcap-runtime-authorization.md) examines runtime authorization. Internal refusal and external permission checks answer different questions.

## Free-to-run check and usage status

Proposed, free and unrun: use hand-written benign output fixtures and a mock tool to distinguish an explicit refusal, harmless completion, malformed response and unauthorized attempted action. Record task completion, policy decision and tool effect independently. The mock tool should reject unauthorized actions even if the text sounds compliant. This tests local reporting and enforcement only; it does not reproduce the neural mechanism.

Proposed / untrialed / not adopted. No weights, activation interventions, jailbreak prompts or model runs were used.

## Unconfirmed points and next checks

Before drawing deployment conclusions, evaluate the actual model version and surrounding controls. Keep classifier error, system-prompt settings, benign-task regressions and untested model families explicit. A negative refusal-string check is not a safety result.

[Category index](README.md) | [Reading list](../../docs/reading-list.md)
