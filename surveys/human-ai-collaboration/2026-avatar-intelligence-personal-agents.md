**English** | [日本語](2026-avatar-intelligence-personal-agents.ja.md)

# Avatar Intelligence and oversight of persistent personal agents

## Overview

- **What it is** Position paper about personal agents that carry goals, preferences and limits across tasks.
- **What it says** It proposes four stages of delegation, an oversight-adjusted score and a way to rehearse user-specific decisions.
- **Caveat** The roadmap and Agentic Oversight Index (AOI) are proposals. Their real-world effects need empirical evaluation.

## Practical reading (six lines)

- The paper asks how agents can reduce routine supervision while users retain authority over consequential decisions.
- The four stages range from user-directed work to autonomy within delegated domains, with delegation revocable throughout.
- AOI subtracts a weighted measure of human oversight from normalized delivered value net of agent-side cost.
- Rehearsal Engineering uses representative scenarios and feedback to update how the agent acts across tasks.
- A proposed harness trial compares draft-only workflows by outcome quality, operating cost, correction time and review load.
- AOI depends on task-specific scales and weights. Component measures make its interpretation easier to audit.

## Bibliography and reading scope

Zheng Wu, Xinbei Ma, Yao Yao, Zhaoyuan Huang, Haowen Hu, Yijie Lu, Taolei Wang, Yifei Yang, Wuyue Xiong, Pengzhou Cheng and Zhuosheng Zhang. arXiv:2611.03092v1, 2026-11-02. Partially read on 2026-11-11 JST, covering §§2 and 4 and Appendix B.

## Method, evidence and limitations

The roadmap allows distinct autonomy levels for different domains. AOI compares human oversight against a human-only baseline and penalizes oversight separately from agent resource cost. The paper also proposes staged rehearsal using representative user situations to improve memory, skill choice and decisions. How to weight oversight and maintain stable preferences as circumstances change remains open.

## Related work

The agent memory notes describe mechanisms for retaining state across sessions. This paper asks what decision authority an agent should have when it uses that state and how much review its work creates.

- [Goals as first-class abstractions](2026-goals-first-class-abstractions.md)
- [Components of agent memory](../llm-infrastructure/2026-anthropic-agent-memory-components.md)

## Free check and usage status

Proposed, untried. Use fictitious reading requests and prewritten examples of preferences, ambiguous instructions and corrections. Compare a fixed workflow and a rehearsed workflow under identical draft-only permissions. Record accepted drafts, review minutes, corrections and agent cost before aggregating AOI. Next check sensitivity to weights and use held-out scenarios to measure whether adaptation generalizes.

## Primary sources

- [arXiv record](https://arxiv.org/abs/2611.03092v1)
- [HTML full text](https://arxiv.org/html/2611.03092v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
