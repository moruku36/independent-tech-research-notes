**English** | [日本語](2026-ctfusion-live-ctf-evaluation.ja.md)

# CTFusion: evaluating security agents using live CTFs

## Overview
- **What it is:** Research on an evaluation framework for LLM agents using Capture The Flag security competitions.
- **What it reports:** The authors observed higher solve rates on a static benchmark than in five live competitions.
- **Caveat:** Difficulty and contamination effects cannot be separated; models, agents and competitions are limited.

## Source and scope
Dongjun Lee, Ga-eun Bae and Insu Yun, [CTFusion: A CTF-based Benchmark for LLM Agent Evaluation](https://arxiv.org/abs/2605.11504v2), arXiv:2605.11504v2, revised 11 July 2026 (v1: 12 May). The arXiv metadata title differs from the [HTML title](https://arxiv.org/html/2605.11504v2), “CTFusion: A CTF Based Benchmark for Evaluating LLM Agents via MCP”. arXiv records acceptance at the ICML 2026 AIWILD workshop and a camera-ready revision. Checked 2 November 2026 JST: selected primary HTML abstract, design, setup, results and limitations. Code and PDF not checked; no reproduction.

## Question and method
Public write-ups and possible training contamination can distort evaluation on old CTF tasks. CTFusion connects agents to live CTFd competitions via MCP, keeping separate agent progress under one account and forwarding only the first correct flag for each challenge. The study examines five online 2025 competitions, three models and two agents, EnIGMA and D-cipher, alongside 180 retained NYU CTF Bench problems.

## Results and interpretation
Under up to three attempts per problem (pass@3) and about $3 per attempt, average GPT-4.1 solve rates were 7.10% across five live competitions and 16.94% on the static benchmark. The tasks and aggregation differ; task difficulty and contamination cannot be separately quantified. The authors also observed an augmented search-enabled agent retrieve public write-ups and flags, but this does not prove all of the gap is caused by cheating or contamination. The static EnIGMA average is 16.8% in Section 5.2 and 16.30% in Section 5.3; the reason is unresolved. Limited live repetitions preclude reliable confidence intervals.

## Proposed applications
Evaluate security agents with authorized isolated fresh tasks alongside public benchmarks. Record sources, tool use, attempts, budget, difficulty and potential answer leakage. Do not generalize CTF scores to real-world attack or defense performance. Follow competition rules and authorization.

## Limits
The evaluation covers three commercial models, two agents and five CTFd competitions under time and cost constraints. Applicability to other competition formats or production systems is unverified. No independent validation, reproduction or adoption.

[AI agent safety index](README.md)
