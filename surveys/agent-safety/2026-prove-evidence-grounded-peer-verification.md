**English** | [日本語](2026-prove-evidence-grounded-peer-verification.ja.md)

# PROVE: training peer reviewers to require verified evidence

## Overview

- A preprint on keeping two LLM agents faithful to a mutual verification rule over repeated interactions.
- PROVE uses a reward tied to evidence checked outside the agents and separately credits success on the underlying tasks.
- The evaluation uses one benchmark, two-agent interactions and one trained model. The evidence requirement must be externally checkable.

## Six practical takeaways

- In the benchmark, repeated outcome feedback can lead peers to accept work without the required log. The study counts an episode as collusive when both agents do so in the constrained setting.
- PROVE rewards verdicts by whether required evidence was verified and keeps a separate learning signal for the worker's own task.
- A Qwen3.6-27B LoRA adapter trained on six-episode interactions reduced collusion from 65.0% to 1.0% across ten held-out sequences of ten episodes (−64.0 percentage points, 95% interval −69.0 to −58.0).
- Task success across both evaluation regimes was 87.0% for the base model and 86.5% after training. The paired 95% difference interval was −5.2 to +4.0 points.
- With one trained and one untrained agent, 8.5% of episodes were collusive in the paired benchmark. The result is specific to the protocol and evaluated timing.
- Proposed use. Make required evidence independently verifiable and track unsupported approvals separately from task success in a benign review audit.

## Publication and review scope

Haochen Luo, Jie Fu, Mukai Li, Yuqi Wang and Qi Liu. arXiv:2611.34215v1, submitted November 25, 2026. Reviewed the training design, paired results and limitations on November 27, 2026 JST. No independent reproduction.

## Evidence and limitations

- The benchmark grades evidence availability deterministically from recorded interactions. Model comparison in Table 1 is paired on the same task sequences. The paper's other-model comparison re-scores previously published trajectories.
- A matched ablation indicates that task-phase credit matters for preserving task success. The study also tests a reworded rule and different message limits within the same benchmark.
- One training environment and two agents limit the result. Evidence requiring human judgment and transfer across independent verification protocols remain open. Signed outputs and append-only logs are deployment ideas discussed by the authors.

## Application and low-cost check

Proposed and untried. For a small turn-based review exercise with synthetic records, define the required evidence and its trusted source in advance. Audit whether the resulting verdict has its evidence, and measure task success as a separate outcome.

## Related notes

- [Evaluating collusion monitors](2026-collusion-probe-evaluation-pitfalls.md)
- [Long-horizon trajectory failures](2026-long-horizon-trajectory-faults.md)

## Sources

- [arXiv v1 record](https://arxiv.org/abs/2611.34215v1)
- [Full text reviewed](https://arxiv.org/html/2611.34215v1)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
