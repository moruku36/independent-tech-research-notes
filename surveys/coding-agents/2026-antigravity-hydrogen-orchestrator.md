**English** | [日本語](2026-antigravity-hydrogen-orchestrator.ja.md)

# Hydrogen and Orchestrator in Google Antigravity

## Overview

- **What it is** Antigravity’s announcement of Hydrogen and its Orchestrator model option.
- **What it says** Orchestrator switches between Carbon planning and Hydrogen execution within a session.
- **Caveat** The reported gains are provider evaluations. Benchmark versions differ across the inspected announcement pages.

## Practical reading (six lines)

- Carbon can inspect a task and produce a plan with replanning triggers.
- Hydrogen edits code and runs checks, escalating when needed.
- This complements Swarm’s parallel agents and separate worktrees.
- The article describes Hydrogen for paid Pro and Ultra, with Orchestrator initially for Ultra.
- A proposed comparison measures task success, wall time and quota on the same work.
- Plan availability and benchmark configuration need to be pinned with the results.

## Source and reading scope

The Antigravity Team, 2026-11-12. Checked 2026-11-13 JST. Direct web retrieval failed. The official Japanese-rendered article was read in the browser and checked against the changelog and Google announcement.

## Content, evidence and limitations

The article describes bidirectional model switching and SDK-defined role assignment. Its Japanese text labels the comparison Terminal-Bench 4.1, while the broader Google announcement labels it 4.0. The relationship between those measurements has not been resolved here.

## Related notes

- [Gemini 4 Hydrogen launch](../articles/2026-google-gemini-4-hydrogen.md)
- [RIVET routing](../llm-infrastructure/2026-rivet-multiturn-llm-routing.md)
- [Swarm user report](2026-antigravity-swarm-reddit-report.md)

## Free check and usage status

Proposed, untried. Use one owned edit task with fixed checks and compare a single model, Orchestrator and a bounded parallel workflow. Record completed checks and consumption. Next confirm rollout, benchmark version and how state is retained across model switches.

## Sources

- [Submitted Antigravity article](https://antigravity.google/blog/gemini-4-hydrogen-in-google-antigravity/)
- [Google model announcement](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- [Official changelog](https://antigravity.google/docs/changelog/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
