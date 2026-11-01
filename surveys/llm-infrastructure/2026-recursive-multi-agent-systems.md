**English** | [日本語](2026-recursive-multi-agent-systems.ja.md)

# Recursive Multi-Agent Systems: collaboration through latent states

## Overview
- **What it is:** A research preprint and an article describing multi-agent communication through latent representations.
- **What it reports:** Under evaluated conditions, the authors report lower inference time and output-token use than text-based recursion with the same architecture.
- **Caveat:** The approach needs model internals and trained connectors; results do not automatically transfer to existing API-based agents.

## Sources and scope
[ToKnow.ai article](https://toknow.ai/posts/recursive-multi-agent-systems-latent-space-recursion-uiuc-stanford-nvidia-mit/) by Charles Kabui, 5 June 2026, describes [Recursive Multi-Agent Systems](https://arxiv.org/html/2604.25917v2) by Jiaru Zou, Rui Pan, Ruizhong Qiu, Pan Lu, Shizhe Diao, Jindong Jiang, Hanghang Tong, Tong Zhang, Markus J. Buehler, Jingrui He and James Zou, arXiv:2604.25917v2, 13 July 2026. Article and paper are one research record. Checked on 2 November 2026 JST: article text and selected v2 abstract, method, main table and results. V2 postdates the article; changes from v1 were not compared. Code, PDF and reproduction not checked.

## Question and method
Text-based agents serialize intermediate thoughts. RecursiveMAS uses trainable RecursiveLink modules to transfer latent states among heterogeneous agents over multiple rounds before producing the final text. It freezes the backbone models and trains the connectors. The paper studies sequential, mixture, distillation and tool-using deliberation patterns.

## Results and interpretation
The authors evaluate nine benchmarks spanning mathematics, science, medicine, search and code. Against text recursion with the same agent architecture and number of rounds, Table 2 reports average 1.2–2.4× inference speedup and 34.6–75.6% fewer output tokens over one to three rounds, conditional on the measured configurations. The article attributes 86.7% versus 73.3% to AIME 2026; in the checked v2 Table 2 those numbers are for **AIME 2025**, scaled configuration and three-round Pass@10, while AIME 2026 is 86.0% versus 74.7%. The reason, including possible version differences, remains unverified.

## Proposed applications and limitations
Measure intermediate text volume, latency, task quality and auditability when evaluating team communication. Latent transfers require separate consideration of explainability, approvals and security. This is a proposal, not a demonstrated production benefit. Training connectors and accessing hidden states are required; results on selected models and nine benchmarks do not generalize automatically to commercial APIs or every task. The article's broad claim about communication as the cause of collaboration failures is not established as a universal conclusion. No independent verification, reproduction or adoption.

[LLM infrastructure index](README.md)
