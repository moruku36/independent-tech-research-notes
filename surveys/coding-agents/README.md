**English** | [日本語](README.ja.md)

# Coding agents, code review, and software engineering

Benchmarks and industrial studies of AI coding assistants, automated repair, and automated review.


## Added 2026-11-14

- [Rust 1.100: language, allocation and Cargo changes](2026-rust-1-100-release.md) — Official release article. Selected compatibility and Cargo changes checked.
- [CAMP-II: learning file-based memory across context boundaries](2026-camp-ii-file-memory-distillation.md) — Preprint v2. Training method and gain denominator checked.
- [ParallACT: coordinating independent requests in shared code](2026-parallact-shared-code-coordination.md) — Preprint v1. Joint correctness and comparison conditions checked.

## Added 2026-11-13

- [Why Writing Correct Software Is Hard](2016-correctness-and-complexity.md) — 2016 technical essay. Selected arguments checked.
- [Hydrogen and Orchestrator in Google Antigravity](2026-antigravity-hydrogen-orchestrator.md) — Official product article. Browser text checked.
- [A Reddit user’s Swarm development trial](2026-antigravity-swarm-reddit-report.md) — Community account. Official workflow cross-checked.

## Added and rechecked 2026-11-12

- [GitHub’s Git infrastructure for agent-scale development](2026-github-git-infrastructure-agent-scale.md) — Engineering article. Architecture and internal benchmark scope checked.
- [The Agentic Scientist and evidence-based research orchestration](2026-sakana-agentic-scientist.md) — Preprint v1. Workflow and limitations checked.

## Added 2026-11-11

- [CWE-bench and evaluation of defensive repository repair](2026-cwe-bench-defensive-repair.md) — Benchmark preprint v2. Repair criteria and Table 3 checked.
- [AlphaProof Code and machine-checked guarantees for libsignal](2026-google-alphaproof-code.md) — Announcement and selected technical-report sections checked.
- [Evan X. Merz on AI-assisted codebase fragility](2026-merz-ai-codebase-fragility.md) — Practitioner essay, with no controlled measurement.

## Added 2026-11-10

- [AI discovery of formally verified quantum programs](2026-formally-verified-quantum-discovery.md) — Preprint v2; frozen-specification verification and resource metrics partially checked; not reproduced.
- [Organon: adapting the procedure of scientific search](2026-organon-scientific-discovery.md) — Primary source partially checked; not reproduced.

## Added 2026-11-09

- [How Effectively Do Security Skills Guide Coding Agents in Vulnerability Detection in Linux Kernel?](2026-security-skills-kernel-skill-sif.md) — Preprint v1; file-guided audits and skill refinement partially checked; absolute rates distinguished from multipliers; not reproduced.
- [Do AI Coding Agents Write Infrastructure as Code Like Humans? An Empirical Study of GitHub Pull Requests](2026-agent-iac-pull-request-study.md) — Observational preprint v1; attribution and within-repository comparisons checked; reporting differences recorded; no reanalysis.

## Added 2026-11-08

- [What Open-Source Projects Tell Their Coding Agents: A Census of AGENTS.md and CLAUDE.md](2026-agents-claude-instruction-file-census.md) — Observational preprint v2; root-file prevalence/content checked; distinguished from effectiveness and runtime use.

## Added 2026-11-07

- [Recursive Self-Improvement through Multi-Agent Self-Supervision](2026-mass-multi-agent-self-supervision.md) — Preprint v1; workflow search and SFT; output-token efficiency distinguished from total cost; not reproduced.

- [The AI Scientist: Towards Fully Automated Open-Ended Scientific Discovery](2024-sakana-ai-scientist.md) — Research article + paper v3; 2024 pipeline and limits partly checked; automated scores distinguished from actual acceptance; not reproduced.
- [Darwin Gödel Machine: Open-Ended Evolution of Self-Improving Agents](2025-sakana-darwin-godel-machine.md) — Research article + paper v3; code self-improvement with frozen models; staged and full evaluations distinguished; not reproduced.

- [Beyond Accuracy: How Quantization Affects Coding Agents](2026-quantization-coding-agent-behavior.md) — Preprint; primary methods and main tables checked; non-significance distinguished from equivalence; not reproduced.

## Added October 28, 2026

- [Scion commentary: Git assumptions at agent scale](2026-scion-qiita-design-review.md) — Practitioner commentary on a primary engineering article. Body and publication metadata read through Qiita's API. Primary Scion article has an existing note; figures and additional Entire claims were not independently rechecked.
- [How harness distillation changes agent engineering](2026-harness-distillation-commentary.md) — Technical commentary, republished from Arize. Article body returned by search checked; primary Harness-Zero/RRSI papers and experiments not independently checked.
- [Modern AI: from language models to thinking systems](2026-thinking-systems.md) — IBIS tutorial presentation. Description and major transcript sections partially checked; diagrams and cited studies not independently validated.

- [Microsoft agentic code migration and specification-driven development](2026-microsoft-agentic-code-modernization.md) (2026-10-26): company engineering article; primary text checked; migration and proofs not independently verified or reproduced.

- [How the Claude Code team does code review](2026-claude-code-review.md) — Company engineering article; primary article checked, X/PDF content not independently verified; no reproduction.

- [Redesigning source control at Anthropic](2026-anthropic-scion-source-control.md) — Research report / technical article reading note. Partially reviewed; no reproduction.

- [When to fold subagents into the main loop](2026-fold-subagents-main-loop.md) (2026-10-22): technical article; body checked, migration kit not run. Counted separately from research papers.
- [Neuro-Formal Verification](2026-neuro-formal-verification.md) (v1, 2026-08-21): preprint; method, evaluation, and error analysis checked; partial reading, no reproduction.

- [LLM-assisted formal software verification](2026-anthropic-formal-verification.md) (2026-10-22): Anthropic research article; primary sources checked, no independent verification or reproduction. Counted separately from academic papers.

- [SlopCodeBench: code degradation under iterative agent development](2026-slopcodebench.md) (v2, 2026-05-07): 36 problems and 196 checkpoints measuring correctness, structural erosion, and verbosity. Primary PDF body, main tables, and execution conditions checked; no reproduction.
- [SWE-Journey](2026-swe-journey.md) (2026-10-08): long-horizon development with simulated user dialogue. Primary text checked; partially read.
- [FlowAgent](2026-flowagent.md) (2026-10-05): low-latency automatic repair of pre-submit test failures at Google. Primary HTML read in full; no reproduction.
- [From Human-Centric to Agentic Code Review](2026-agentic-code-review-eras.md) (v1, 2026-07-14): 1.02M reviewed PRs across human-centric, assistant-augmented, and agentic review eras. Primary PDF text checked.
- [Adoption and Impact of Command-Line AI Coding Agents](2026-cli-coding-agents-adoption-impact.md) (v1, 2026-07-01): telemetry and survey (n=3,812) on terminal coding agents at Microsoft. Primary PDF text checked.
- [Automating Low-Risk Code Review at Meta: RADAR](2026-radar-low-risk-code-review.md) (v2, 2026-06-12): risk-stratified automated review and landing across 535K+ diffs at Meta (DRS + LLM ACR). Primary PDF text checked.

[Survey index](../README.md) | [Repository README](../../README.md)

- [Minimal harness for autonomous ML engineering](2026-ml-engineering-minimal-harness.md) — primary HTML selected sections; benchmark-specific results, no reproduction.

- [Evolving Agent Teams](2026-evolving-agent-teams.md) — selected primary HTML sections checked; discrepancies recorded; not reproduced.

- [AutoHarness: synthesized action verification](2026-autoharness-code-synthesis.md) — primary HTML selected sections; finite game tests, not reproduced.


- [Structured output failures](2026-structured-output-failure.md) — selected primary text checked; no reproduction.
