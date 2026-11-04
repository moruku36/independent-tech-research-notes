**English** | [日本語](2026-autonomous-agents-ctf-second-look.ja.md)

# Autonomous LLM agents and CTFs: a second look

## Overview
- **What it is:** A study comparing agent architectures on web-security CTF challenges.
- **What it reports:** General-purpose and engineered agents each solved at most 19 of the 30 selected tasks.
- **Caveat:** Model and trial counts differ; CTF results do not directly establish general real-world or human-relative capability.

## Source and scope
Youness Bouchari, Matteo Boffa, Marco Mellia, Idilio Drago, Thanh Minh Bui and Dario Rossi, [Autonomous LLM Agents & CTFs: A Second Look](https://arxiv.org/html/2605.21497v1), arXiv:2605.21497v1, submitted 29 April 2026. arXiv reports acceptance at the IEEE EuroS&P 2026 DeMeSSAI workshop. Selected primary HTML setup, tables and discussion checked 4 November 2026 JST. Code and PDF not checked; no reproduction.

## Question and method
The authors revisit claims of near-human CTF performance using 30 selected XBOW web challenges across 14 vulnerability classes. They compare a single executor, executor plus evaluator, planner/executor/evaluator, and a general-purpose Claude Code baseline. Engineered configurations run three independent times per task; Claude Code is run once due to cost and usage limits, with up to 50 steps per run.

## Results and conditions
All GPT-5 engineered configurations reached 19/30 when counting a task solved at least once across three runs; Claude Code with Opus 4.5 reached 19/30 in one run. These counts use different trial budgets. Within GPT-5 configurations, planner/executor/evaluator solved 16/30 consistently across all three runs versus 12/30 for the executor, with average cost $0.59 versus $0.90, but average duration 925.80 versus 336.74 seconds. Missing browser execution and other environment capabilities contributed to some failures.

## Proposed applications and limitations
In authorized isolated evaluations, record repeated-run consistency, cost, time, available tools and solved-task coverage. Compare with [CTFusion](2026-ctfusion-live-ctf-evaluation.md), which also raises answer leakage in public tasks. These benchmarks do not establish general real-world offensive or defensive performance, or universal human-relative capability. Independent validation, reproduction and adoption were not performed.

[AI agent safety index](README.md)
