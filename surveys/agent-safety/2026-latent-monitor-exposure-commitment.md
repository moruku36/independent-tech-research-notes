**English** | [日本語](2026-latent-monitor-exposure-commitment.ja.md)

# Exposure is not commitment in agent-monitor evaluation

## Overview
- **What it is:** A preprint evaluating monitors of unsafe tool-using agent behavior using model activations.
- **What it reports:** Separating exposure to an attack from commitment to an unsafe action in both training and evaluation improves pre-action prediction.
- **Caveat:** A trained text baseline performs similarly under matched conditions; results do not prove production safety.

## Source and scope
Rishabh Sinha, [Exposure Is Not Commitment: Double-Stratified Evaluation of Latent Monitors for Tool-Using Agents](https://arxiv.org/html/2610.37679v1), arXiv:2610.37679v1, submitted 12 October 2026. arXiv records acceptance as a NeurIPS 2026 AIWILD workshop poster. The supplied title omitted the first part of the official title. Checked 4 November 2026 JST: selected primary HTML experiments, tables and limitations. Code and PDF not checked; no reproduction.

## Question and method
An agent's exposure to malicious text differs from its actually following it into an unsafe tool call. A mixed evaluation can reward detection of the attack's presence rather than prediction of unsafe behavior. The author stratifies both training and evaluation and compares classifiers using internal activations with visible-text baselines.

## Results and limits
On Qwen's AgentDojo-grounded generated-action grid, among 240 attacked trajectories (141 unsafe and 99 safe), the pre-action logistic activation probe achieved AUROC 0.853; a trained TF-IDF text classifier achieved 0.855 under the same contrast. AUROC measures ranking, not production safety or false-alarm rate. Trajectories have three steps, allowing at most two steps of lead; this was not a live environment rollout. One benchmark, non-adaptive attacks and limited model families constrain generalization; clean-traffic false-alarm cost was not measured, and activation access is unavailable for most frontier APIs.

## Proposed applications
Label attack exposure, attempted unsafe action and safe refusal separately; also measure false alarms on normal traffic. Include text/log baselines and combine monitoring with authorization and approvals. This is a proposal, not a validated outcome in the user's environment. No independent verification or reproduction.

[AI agent safety index](README.md)
