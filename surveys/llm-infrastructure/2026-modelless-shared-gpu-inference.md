**English** | [日本語](2026-modelless-shared-gpu-inference.ja.md)

# ModelLess: lending idle GPUs across inference tiers

## Overview

- An Ant Group technical report on sharing GPUs across latency-sensitive and interruption-tolerant LLM inference products.
- ModelLess releases idle GPUs while keeping model weights in host memory. Tiers define what state and work are kept when resources are reclaimed.
- Fleet capacity is an upper-bound estimate from replay. The node experiment covers one borrower workload and one run per policy.

## Six practical takeaways

- Idle model instances sleep with weights in host memory, freeing GPUs for lower-priority work.
- For GLM-5.2 with tensor parallelism across eight GPUs, release took about 1 second and wake about 4 seconds. The reported cold start took over four minutes.
- The regular-week trace of 1,100 H20 GPUs gave a 37.9% lendable GPU-time estimate with a 60-second idle threshold and a median-and-timeout gate.
- In one four-hour run per policy on one node, pause and resume delivered 22% more borrower tokens per held-GPU sample than abort and requeue.
- Median online time to first token was similar, but p99 was 10.1 seconds with pause and 11.2 seconds with requeue. The stricter tail gates failed in both runs.
- Proposed use. Compare replayed and measured capacity and report tail latency, timeout rates and progress preserved on interruption.

## Publication and review scope

Ding Shi, Wei Wu, Jiayuan Chen and Chenghu Yang, Ant Group. arXiv:2611.32634v1, submitted November 24, 2026. Reviewed the design, Tables 7–9 and 13, and limitations on November 27, 2026 JST. No independent reproduction.

## Evidence and limitations

- The platform distinguishes online, job and flex tiers by the state that can be lost under preemption, including weights, engine state, KV cache and in-flight requests.
- The 417 GPU-equivalent estimate concerns a selected group of long-tail online services. The replay's coarse median-and-timeout gate and fixed idle threshold matter for interpretation. It does not fully account for borrower yield on the owner's latency path.
- The one-node comparison used 64K-token inputs for the borrower. Long requests stand to gain from preserving decode progress. The job tier and rollout weight-transfer path were not evaluated end to end.

## Application and low-cost check

Proposed and untried. Replay a synthetic request trace under several wake delays and idle thresholds. Track the share of time that can be lent, online time to first token and timeouts, then compare these estimates with controlled measurements if hardware is available.

## Related notes

- [TideSand sandbox multiplexing](2026-tidesand-sandbox-multiplexing.md)
- [AdaOffload adaptive CPU–GPU inference](2026-adaoffload-multi-gpu-moe.md)

## Sources

- [arXiv v1 record](https://arxiv.org/abs/2611.32634v1)
- [Full text reviewed](https://arxiv.org/html/2611.32634v1)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
