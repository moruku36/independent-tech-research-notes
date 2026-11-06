**English** | [日本語](2026-quantization-coding-agent-behavior.ja.md)

# Beyond Accuracy: How Quantization Affects Coding Agents

## Overview

- Preprint comparing the accuracy, trajectories, and failures of 4-bit coding agents.
- No significant accuracy loss was detected after correction, while tool use and failure profiles changed across models.
- Evaluation uses 115 Python competition problems and one execution loop; it does not establish equivalence or production speedups.

## Practical reading (7 lines)

- The study asks whether final correctness is enough to evaluate a quantized coding agent.
- It compares three Qwen2.5-Coder sizes and Devstral under BF16, AWQ, and GPTQ.
- Corrected and problem-level analyses detect no statistically significant accuracy loss.
- Qwen-7B nevertheless shifts from one-shot solutions toward execution-and-revision loops.
- Proposed application: record tool calls, failure categories, and total latency before adoption.
- A non-significant difference is not proof of equivalent quality; test the required quality threshold.
- Generalization to other languages, scaffolds, and operational cost remains unverified.

## Source and verification scope

- Original title: Beyond Accuracy: How Quantization Affects Coding Agents.
- Authors: Areej Mehboob, Muhammad Ali Shafique, Muhammad Usman Qadeer, Hamza Farooq.
- arXiv:2611.02368v1, 2026-11-02. The arXiv comments report acceptance at the NeurIPS 2026 SLM-Agents workshop; venue-side confirmation was not checked.
- Checked 2026-11-07 JST: primary HTML setup, main findings, statistical methods, main appendix tables, and limitations. Status: partially read; not reproduced.

## Research question

How does 4-bit weight quantization affect correctness and behavior in execution-feedback coding agents?

## Method, data, and comparison conditions

Compare Qwen2.5-Coder-Instruct 7B/14B/32B and Devstral-Small-2507 24B at BF16, W4A16 AWQ, and GPTQ. Evaluation uses 115 OJBench Easy/Medium problems in Python, three seeds, and up to five tool calls. Hard is excluded because every configuration scores zero. Statistical analyses address multiple comparisons and correlated seeds within problems.

## Claims and evidence

Table 1 reports Qwen-32B mean accuracy of 13.91% at BF16 and 10.72% at AWQ, but corrected testing does not detect a significant loss. Solve paths and failure distributions change, motivating behavioral evaluation beyond correctness (§3–5 and Appendix A).

## Limitations and threats to validity

One benchmark, language, scaffold, and limited model pool; modest solve counts constrain statistical power. Non-significance is not an equivalence test. End-to-end latency and working-memory evaluation remain future work.

## Comparison with related work

[NVIDIA's memory codesign](../llm-infrastructure/2026-nvidia-memory-full-stack-codesign.md) addresses capacity and throughput; this study examines behavior after reduced precision. [Ignored, Not Refused](../agent-safety/2026-ignored-not-refused-prompt-injection.md) likewise separates scalar scores from behavior.

## Free-to-run verification plan and usage status

Proposed, not performed: where local inference already exists, compare precision settings on a small public Python task set, recording correctness, executions, time, and tool-format errors. If free compute is insufficient, analyze public traces instead. Usage status: proposed.

## Open questions and next checks

Check released code and checkpoints, recompute statistical tables, and examine other languages, realistic tasks, memory, and latency.

## Primary sources

- [Supplied URL](https://arxiv.org/abs/2611.02368)
- [Primary HTML version examined](https://arxiv.org/html/2611.02368v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
