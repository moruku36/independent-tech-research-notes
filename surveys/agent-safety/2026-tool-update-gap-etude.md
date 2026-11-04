# Beyond Prompt Injection: The Tool Update Gap in LLM Agent Security

[日本語](2026-tool-update-gap-etude.ja.md) | [Theme index](README.md)

- **Source:** [arXiv:2611.01976v1](https://arxiv.org/html/2611.01976v1), preprint, 1 November 2026.
- **Authors:** Shiyu Kan, Yue Qi, Yufei Han, Xinjian Luo, Guojun Xiong, Xiaofeng Gao.
- **Scope:** Main text and experimental setup reviewed; no independent code inspection or reproduction.

## Summary
ETUDE studies malicious updates to an already authorized tool. The attacker controls its release channel and the agent accepts updated code under existing permissions; this is different from merely inserting instructions in retrieved text.

## Method and findings
In isolated tests with synthetic credentials, a local receiver, isolated files and test APIs, the authors evaluate seven agent frameworks and multiple models. In the RQ1 comparison, 21 equally weighted framework–workload conditions (seven by three), each with five rounds of 20 planned calls, yield 2,100 planned calls. ETUDE reports 100.0% attack success and 99.6% final-output completion versus 20.2% and 96.4% for the strongest prompt-only baseline. The evaluation uses a simulated admission gate and assumes malicious updates are accepted, with approvals where required. These figures are conditional laboratory results, not a real-world compromise probability.

## Practical interpretation
Pin tool versions, review and authorize changes before rollout, restrict runtime permissions and isolate tool execution. Signed releases can establish provenance, but signatures alone do not prove code is safe. Prompt scanning alone cannot inspect behavior executed directly by a tool.

## Limits
The attack requires release-channel control and adoption of the update. Measured rates depend on frameworks, models, tasks and the simulated environment; effectiveness against a particular production deployment is unverified.
