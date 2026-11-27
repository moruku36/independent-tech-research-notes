**English** | [日本語](2026-timetravelcontainer-live-forking.ja.md)

# TimeTravelContainer for live forking of stateful tool sessions

## Overview

- An arXiv preprint presenting TimeTravelContainer (TTC), a rootless runtime that forks live tool sessions with copy-on-write.
- The authors report faster environment cloning and faster repeated tool calls in two electronic design automation (EDA) workflows.
- The benchmarks replay fixed tool workloads on Linux and exclude LLM inference. The results cover those tool workloads.

## Six practical takeaways

- TTC extends gVisor so a running tool can be branched with its initialized process and container state.
- Branches share unchanged memory pages and files. Memory savings depend on how much the branches change after the fork.
- On MAGE with Innovus, Ariane133 clone readiness fell from 86.5 s to 1.03 s. BlackParrot went from 185.7 s to 3.01 s.
- In EvoDRC with KLayout, ten-call runs were 1.7–2.1 times as fast on small designs and 8.0–9.7 times as fast on large designs according to Table V.
- The strongest fit is repeated exploration with expensive startup and short per-branch work. The tests used fixed replays and excluded model latency.
- A local trial could separately measure time to clone readiness, memory after branch changes, and the elapsed time for a fixed series of tool calls.

## Source and verification scope

- Primary source checked on 2026-11-28. The method and evaluation tables in v1 were reviewed.
- Zizheng Guo, Yanqing Zhang, Nathaniel Pinckney, Cunxi Yu, and Brucek Khailany. *TimeTravelContainer: A Live Forking Sandbox for Stateful Agent Exploration*. arXiv:2611.32255v1, 2026-11-24.
- [arXiv record](https://arxiv.org/abs/2611.32255) · [v1 full text](https://arxiv.org/html/2611.32255v1) · [authors’ implementation](https://github.com/NVlabs/TimeTravelContainer)

## Evaluation and comparison

MAGE compares creating an independent usable session with saving and restoring an Innovus checkpoint. The authors used the same readiness query. EvoDRC compares a prepared KLayout environment that forks for each candidate with relaunching KLayout. The authors checked that geometry, rule reports, and repair verdicts matched.

## Reading the tables

In Table IV, total resident memory savings span 24–72% across the listed cases. For six BlackParrot branches after edits, memory fell from 62.4 GB to 40.9 GB. Table V reports 9.7× for the ten-call Ibex run and 9.4× for JPEG. The abstract and conclusion cite 9.4×, so this note uses the table for the observed range.

## Scope and related work

All timing experiments ran on Linux servers. The paper describes Apple Silicon and WSL 2 support separately. [SWE-agent](../coding-agents/2024-swe-agent-computer-interface.md) studies how agents interact with tools. TTC changes how the state behind that interface can be branched.

## Proposed local check

Use a disposable open-source workload with a warm in-memory state. Compare fresh startup with a prepared fork, verify identical outputs and branch-local file changes, and measure memory after edits. Status is proposed. Timing, platform support, and isolation guarantees have not been independently verified.
