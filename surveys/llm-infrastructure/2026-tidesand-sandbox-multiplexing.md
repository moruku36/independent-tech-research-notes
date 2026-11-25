**English** | [日本語](2026-tidesand-sandbox-multiplexing.ja.md)

# TideSand: sharing sandbox resources while preserving measurements

## Overview

- A systems preprint on scheduling shared sandbox resources for LLM agents that depend on reliable tool measurements.
- TideSand combines agent-aware scheduling, speculative memory swapping, and selective rollback. The authors compare fidelity and throughput against reservation and overcommit baselines.
- Results are for six model–workload pairs. The work evaluates execution fidelity and throughput under the tested conditions.

## Six practical takeaways

- An agent sandbox can sit mostly idle during inference, then contend for resources in a burst when a tool call runs.
- TideSand uses tool-call timing to admit work, stages waiting sandboxes' memory, and can roll back selected calls when contention occurs.
- Fidelity compares tool timing and outcomes with a reference run that has its configured resources without other sandbox contention.
- Across six model–workload pairs, the authors report 3.8–10× the throughput of strict reservation while preserving fidelity, or 7–44% higher fidelity at similar throughput as overcommit baselines.
- In a replay of 32 scored AlgoTune tasks, the mean reward shift versus strict replay was +77% for overcommit and −4% for TideSand.
- Proposed use. Measure wait time, tool latency and outcome stability alongside task throughput and resource consumption.

## Publication and review scope

Shulu Li et al., arXiv:2611.31118v1, submitted November 23, 2026. Reviewed the abstract, fidelity definition and evaluation on November 26, 2026 JST. No reproduction.

## Evidence and limitations

- The evaluation covers AlgoTune, Terminal-Bench 4.0 and Terminal-Bench Science, with two models across six pairs. Throughput against strict reservation and fidelity against overcommit at similar throughput are different comparisons.
- The AlgoTune analysis replays the same task traces and scores identical final solutions under different sandbox policies. This isolates the effect of measurement contention in the scoring stage.
- The scheduling can exchange queueing time for a cleaner tool run. Workloads with different burst patterns, resource bottlenecks or external side effects warrant separate validation.

## Application and low-cost check

Proposed and untried. Run a benign fixed local task first in isolation and then alongside another job you control. Compare execution-time distributions and outputs while logging queueing delay as its own metric.

## Related notes

- [Cache engineering for agents](2026-cache-engineering-for-agents.md)
- [Routing agent traffic with Envoy](2026-google-cloud-envoy-agentic-stack.md)

## Sources

- [arXiv v1 abstract](https://arxiv.org/abs/2611.31118v1)
- [Full preprint, including measurement and evaluation](https://arxiv.org/html/2611.31118v1)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
