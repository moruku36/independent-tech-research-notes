**English** | [日本語](2026-autoharness-code-synthesis.ja.md)

# AutoHarness: automatically synthesizing action-verification code

## Overview
- **What it is:** An experimental preprint on generating and refining an agent's code harness from game feedback.
- **What it reports:** The authors report no illegal moves in their tests across 145 TextArena games.
- **Caveat:** Finite game trials do not prove safety or correctness in unseen states or real systems.

## Source and scope
Xinghua Lou, Miguel Lázaro-Gredilla, Antoine Dedieu, Carter Wendelken, Wolfgang Lehrach and Kevin P. Murphy, [AutoHarness: improving LLM agents by automatically synthesizing a code harness](https://arxiv.org/html/2603.03329v1), arXiv:2603.03329v1, submitted 10 February 2026. A Google DeepMind-authored preprint. Checked 3 November 2026 JST: selected primary HTML abstract, method, experiments and conclusion. PDF and implementation code not checked; no reproduction.

## Question and method
LLM agents can propose actions prohibited by an environment. Gemini 2.5 Flash generates code that verifies proposed actions, then refines candidates through tree search using environmental legality and error feedback. The main verifier rejects invalid actions and asks for another proposal. A separate code-as-policy variant generates the entire decision policy and does not call an LLM at inference.

## Results and conditions
- The authors report 100% legal actions on new test rollouts for 145 TextArena games, using 10 random seeds per game and up to 1,000 steps. This is finite testing, not a proof for every state.
- End-to-end play covers only 16 single-player and 16 two-player games: 20 and 40 matches per game respectively.
- In the separate code-as-policy experiment on 16 single-player games, mean reward was 0.870 versus 0.844 for GPT-5.2-High; the former had 20 runs per game and the latter five for cost reasons.
- Legality, strategic quality and safety of external actions are separate properties.

## Proposed applications
For proposed cloud changes, explore machine checks of allowed parameters and environment conditions before execution and request revisions for failures. Review the generated verifier and test boundary cases in isolation; retain IAM, approvals and audit as independent controls. This is a proposal, not a demonstrated production result.

## Limits and related work
A separate harness was learned per game, nine free-form games were excluded, and results depend on finite trials, game rules and models. Implementation, reproduction and adoption were not performed. [Minimal harness for ML engineering](2026-ml-engineering-minimal-harness.md) addresses different tasks and objectives and is not directly comparable.

[Coding agents index](README.md)
