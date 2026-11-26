**English** | [日本語](2023-react-reasoning-and-acting.ja.md)

# ReAct: interleaving reasoning, actions and observations

## Overview

- An ICLR paper introducing a prompting method for language models that interact with an external environment.
- ReAct interleaves reasoning text, actions and the resulting observations. Results differ across question answering, fact verification and interactive tasks.
- The experiments use specific models, interfaces and demonstrations. A visible trace helps diagnose errors and can itself contain mistakes.

## Six practical takeaways

- A reasoning step updates the context. Actions retrieve information or change the environment, and observations inform the next decision.
- On FEVER, ReAct reached 60.9% accuracy versus 56.3% for chain-of-thought prompting. On HotpotQA, exact match was 27.4% versus 29.4%.
- Combining ReAct with self-consistent chain-of-thought improved the two benchmark results over standalone ReAct, with the best order differing between tasks.
- In ALFWorld, best-of-six prompting reached 71% with ReAct and 45% with Act. In simulated WebShop, success was 40.0% and 30.1%, respectively.
- The error analysis includes retrieval failures and repeated actions. Tool feedback and traces provide evidence to inspect alongside final answers.
- Proposed use. Compare prompting variants with the same read-only tool interface and budget and log retrieved evidence, completion and failures.

## Publication and review scope

Shunyu Yao, Jeffrey Zhao, Dian Yu, Nan Du, Izhak Shafran, Karthik Narasimhan and Yuan Cao. ICLR 2023, arXiv:2210.03629v3 (March 10, 2023). Reviewed sections 2–4 and Tables 1–4 on November 27, 2026 JST. Experiments were not reproduced.

## Evidence and limitations

- HotpotQA and FEVER used PaLM-540B in a question-only setup. ReAct could use a restricted Wikipedia interface. The table reports exact match for HotpotQA and classification accuracy for FEVER.
- In Table 1, ReAct followed by self-consistent chain-of-thought reached 35.1% HotpotQA exact match. The reverse order reached 64.6% FEVER accuracy. ALFWorld's best-of-six is a prompt-selection result, and WebShop's success rate requires meeting all requested attributes.
- The benchmark outcomes depend on tool coverage and prompt configuration. Empty or unhelpful search results can derail the loop, and a readable trace can express a mistaken inference.

## Application and low-cost check

Proposed and untried. Use a tiny local document collection with known answers. Compare answer-only prompting, tool actions alone, and a reasoning-plus-action prompt under identical query access. Record the supporting documents and characterize missing evidence and repetitive calls.

## Related notes

- [SWE-agent and agent-computer interfaces](2024-swe-agent-computer-interface.md)
- [Claude Code verification practices](2026-claude-code-verification-practices.md)

## Sources

- [arXiv v3 record](https://arxiv.org/abs/2210.03629v3)
- [Full v3 text reviewed](https://arxiv.org/html/2210.03629v3)
- [ICLR 2023](https://openreview.net/forum?id=WE_vluYUL-X)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
