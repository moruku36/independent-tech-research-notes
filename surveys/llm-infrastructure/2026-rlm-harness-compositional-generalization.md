**English** | [日本語](2026-rlm-harness-compositional-generalization.ja.md)

# Recursive language model harnesses and compositional generalization

## Overview

- **What it is**: An alphaXiv preprint on how a language model harness can reuse learned ways of breaking down tasks.
- **What it says**: In the authors’ experiments, recursive language models handled longer or structurally similar tasks, and targeted synthetic training raised the eight-benchmark mean from 46.1 to 58.5 in the same harness.
- **Caveat**: The surrogates were designed for known task families, and the reported token counts alone cannot establish latency or monetary savings.

## Source and reading status

- Paper: *Language Model Harnesses Can Be Compositional Generalizers*, Alex L. Zhang, Souradip Chakraborty and Omar Khattab (MIT CSAIL).
- Published as an alphaXiv preprint (v1, 2026-11-20), identifier `2611.harness-cg`. [Paper page](https://www.alphaxiv.org/abs/2611.harness-cg) | [Author PDF](https://www.alphaxiv.org/abs/2611.harness-cg.pdf)
- Checked on 2026-11-21 JST. Partial reading of the PDF, including Sections 2–4 and Tables 1 and 4–6. No experiment was reproduced.
- Application status is proposed.

## Practical reading (seven lines)

1. The authors ask whether a harness can assemble familiar steps into a solution to an unfamiliar task.
2. An RLM keeps the full input in an external execution environment. Its root model can select slices, process intermediate results and delegate smaller tasks.
3. Short-task reinforcement learning transferred to selected cases with roughly 2–64× longer inputs and to some new domains with similar solution structure.
4. Supervised fine-tuning on targeted synthetic trajectories raised the benchmark mean from 46.1 to 58.5 on the same RLM harness, a gain of 12.4 points or 26.9% relative.
5. Average total input and output fell from roughly 721K to 385K tokens, while output tokens alone increased from about 15K to 65K.
6. For document workflows, compare a single-pass baseline with per-section extraction and aggregation on documents of unseen lengths, using the same model and answer checks.
7. Treat the score and token differences as results for the tested configurations. Measure latency and cost separately on the target workflow.

## Approach and evidence

- **Length and strategy transfer (§3).** The authors trained Qwen3-30B-A3B-Instruct-2507 with GRPO on short inputs and compared the base Transformer, Pi, LM + REPL and RLM. Table 1 includes OOLONG at 32K training and 256K evaluation tokens, and an MRCRv2 setting with up to 64× longer inputs and more retrieval targets. The RLM usually retained more of the short-task gains, while code-based processing sufficed for some tasks. Cross-domain transfer was tested on tasks with similar decomposition structure. Trajectory comparisons and subtask accuracy inform the “locally in-distribution” hypothesis: individual calls can remain familiar and solvable even when the overall task is new.
- **Surrogate training (§4.1–4.2, Tables 4–5).** The authors designed synthetic environments to retain a solution strategy while changing the content, using simulated sub-call responses in some environments. They fine-tuned Qwen3.8-27B into RLM-27B using generated trajectories. Table 4 averages eight held-out benchmark scores equally. The 46.1 → 58.5 comparison uses the same RLM harness. Reinforcement learning on the earlier short-task mix reached 48.5 and reinforcement learning on the synthetic tasks reached 52.9. The two synthetic-training runs also differ in the use of teacher-guided traces, which limits attribution to the learning algorithm. Table 5 reports 18.4 → 6.5 mean root turns. Adding root and sub-call input and output gives about 721K → 385K total tokens, or a 47% reduction based on the rounded table values.
- **Recursive composition (§4.3, Table 6).** Each four-task sequence required a correct answer before the next task was revealed. Across 2,000 sequences sampled from 87 tasks selected for a prior RLM-27B advantage, RLM-27B completed 55.2% of full chains in the standard harness, 47.2% with just a recursion hint and 77.5% after additional supervised training on recursive behavior. The task selection and two-attempt limit per stage constrain the interpretation.

## Related work and comparison

The paper builds on the earlier RLM inference method by training decomposition strategies and testing when they transfer. The [Recursive Multi-Agent Systems note](2026-recursive-multi-agent-systems.md) covers a separate design that exchanges latent states between models. It uses a different architecture and evaluation, so its latency results and this paper’s token counts answer different questions.

## Free-to-start check plan

Build a small synthetic collection of records with known labels and fixed aggregation targets. Hold out both longer lengths and one structurally similar domain. Compare a full-context prompt, external state with ordinary code, and a version that delegates labeling before aggregation, using the same local model and scoring code. Track exact accuracy, root and sub-call tokens separately, elapsed time and failed calls. This is a proposed local check of task decomposition.

## Unconfirmed points and next checks

The held-out instances come from known benchmark families used to design the surrogates. Transfer to unfamiliar families, sensitivity to surrogate quality and end-to-end runtime on local workloads remain open. The code and experiment artifacts remain unexamined.

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
