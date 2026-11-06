**English** | [日本語](2026-ignored-not-refused-prompt-injection.ja.md)

# Ignored, Not Refused: What Low Prompt-Injection Success Rates Hide in Small Tool-Using Agents

## Overview

- Preprint auditing what failed injections mean in small tool-using agents.
- Most failed attacks are ignored rather than refused, and a joint evaluation exposes unfinished user tasks.
- Evidence uses synthetic static attacks, small models, and one LLM judge; it does not establish production security.

## Practical reading (7 lines)

- The study asks whether attack failure alone is enough to call an agent secure.
- It audits 33,000 trajectories from eleven small models on InjecAgent and AgentDojo.
- About 76–80% of failed attacks are ignored rather than explicitly refused.
- Of AgentDojo samples with both verdicts, 21.7% resist the attack but leave the user task unfinished.
- Proposed application: record attack success and task completion in a 2×2 matrix, including format errors.
- Identical weights behave differently under different system instructions, so evaluate the entire configuration.
- Resilience to adaptive attacks and live deployments remains untested.

## Source and verification scope

- Original title: Ignored, Not Refused: What Low Prompt-Injection Success Rates Hide in Small Tool-Using Agents.
- Authors: Farhan Zarif, Kazi Shahid Ahmed Galib, Synthia Akter Promi, Shabnam Sharmin Tarin, Ariyan Hossain, Sadif Ahmed, Farig Yousuf Sadeque.
- arXiv:2610.23254v1, 2026-10-16; venue unconfirmed in checked arXiv metadata.
- Checked 2026-11-07 JST: primary HTML methods, main tables, ATOM, judge validation, and limitations. Released corpus and code not executed or recomputed. Status: partially read; not reproduced.

## Research question

How well does a low indirect prompt-injection attack success rate distinguish refusal, ignoring, inability to act, and user-task completion?

## Method, data, and comparison conditions

One label-blind LLM judge classifies 33,000 trajectories from eleven 2–14B models across two benchmarks. Two authors validate 150 trajectories. ATOM crosses attack success with task completion; additional comparisons vary system policy and inference precision.

## Claims and evidence

Ignored behavior comprises 76.3% of AgentDojo and 80.3% of InjecAgent failed attacks (Table 2). Of 16,273 ATOM-eligible AgentDojo samples, 21.7% are safe but unfinished (Figure 3). Matched prohibitive/permissive system policies yield InjecAgent ASR of 0.22%/43.05% (§4.2); these are not simply before/after baseline values.

## Limitations and threats to validity

Static single-agent attacks and greedy decoding; no adaptive, multi-agent, or live evaluation. One judge and 150 human-checked traces limit validation. Expressed reasoning is not direct access to internal recognition. Ignoring is a behavioral label in these conditions, not proof of future failure.

## Comparison with related work

[Covert safety underperformance](2026-openai-covert-safety-underperformance.md) also motivates measuring task completion alongside apparent safety. [Quantization and coding behavior](../coding-agents/2026-quantization-coding-agent-behavior.md) similarly examines behavior hidden by scalar scores.

## Free-to-run verification plan and usage status

Proposed, not performed: manually label a small public trace sample with harmless injection examples for attack outcome, task completion, refusal, and format errors. Retain ambiguous cases and denominators; no additional model inference is required. Usage status: proposed.

## Open questions and next checks

Check corpus and judge-prompt versions, ATOM denominators and labels, and judge reproducibility.

## Primary sources

- [Supplied URL](https://arxiv.org/abs/2610.23254)
- [Primary HTML version examined](https://arxiv.org/html/2610.23254v1)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
