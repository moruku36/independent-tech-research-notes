**English** | [日本語](2026-ec2-bench-edge-cloud-agents.ja.md)

# EC2-Bench and edge–cloud agent collaboration

## Overview

- **What it is** Benchmark study of long agent tasks split between edge and cloud models.
- **What it says** It compares routing, delegation and cloud advice using task completion, resource use and cloud-visible sensitive information.
- **Caveat** Higher-capability edge models include proxies for future devices. Hardware deployment and privacy guarantees need separate evaluation.

## Practical reading (six lines)

- EC2-Bench contains 128 executable tasks and sensitive-data annotations on 100 tasks.
- It tracks complete execution traces across edge and cloud participation.
- The exposure metric counts annotated information visible in cloud contexts.
- Stronger edge models reduce task-score differences between collaboration strategies.
- Privacy exposure can still vary substantially across those strategies.
- A proposed harness trial compares local-only, delegation and advice on synthetic workspaces.

## Source and reading scope

Pengcheng Huang, Zhenghao Liu, Shixin Ren, Shi Yu, Sijia Yao, Yukun Yan, Chaojun Xiao and Maosong Sun. arXiv:2610.17816v2, revised 2026-10-18. Checked 2026-11-12 JST, selected §§3–6 and privacy-evaluation appendices.

## Method, evidence and limitations

Task completion aggregates weighted requirement checks. Exposure uses annotated units and an LLM judge validated on 200 pairs. Task filtering removes some easy and unsolved cases. Conclusions depend on that task mix, model costs and the distinction between exposure and downstream harm.

## Related notes

- [RIVET](2026-rivet-multiturn-llm-routing.md)
- [Nexus](2026-nexus-cloud-edge-execution.md)

## Free check and usage status

Proposed, untried. Label fictitious sensitive units in a small workspace and record which become cloud-visible under each workflow. Keep success, latency, cost and exposure as separate measures. Next inspect code availability and test on representative tasks.

## Primary sources

- [arXiv record](https://arxiv.org/abs/2610.17816)
- [Inspected v2](https://arxiv.org/html/2610.17816v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
