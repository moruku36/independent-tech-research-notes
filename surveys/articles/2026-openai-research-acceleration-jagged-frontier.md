**English** | [日本語](2026-openai-research-acceleration-jagged-frontier.ja.md)

# Research acceleration: The jagged frontier

## Overview

- **What it is** OpenAI's follow-up report on coding agents in its own research organization.
- **What it says** Estimated autonomous success rose from March to October, with large differences by task.
- **Caveat** Internal observational measures leave the causal effect of agents on research progress unresolved.

## Practical reading (six lines)

- For tasks estimated at two to four hours of human work, zero-intervention success rose from 23% to 46%.
- For the four-to-eight-hour band, it rose from 13% to 35%.
- From August 1 to October 18, monitoring runs reached 79%, starting runs 35%, and inference or serving code 25%.
- In October, median use was equivalent to $2,400 per researcher-day at public API prices.
- Separate experiment volume from validated research outcomes.
- For a local trial, set acceptance criteria by task and record human intervention and rework.

## Source and reading scope

OpenAI, November 18, 2026. Checked November 20, 2026 JST. Read the public report and the task-success methods panel, including its handling of uncertain outcomes. The underlying session records and independent replication were not checked.

## Evidence and limitations

- **Task success.** Human task durations are model estimates. The displayed midpoint gives unresolved outcomes without a recorded intervention half credit. The bounds vary that assumption. The mix of tasks delegated may change over time, even within a duration band.
- **Usage and staff survey.** List-price equivalents value internal usage without observing an invoice. The staff survey's trade-offs are hypothetical.
- **Research output.** Logged experiments per active experimenter were 1.68× the 2025 baseline in the four weeks ending October 18. OpenAI's capability index mixes public and internal benchmarks. These measures do not isolate what agents contributed.

## Application and free check

Proposed and untried. Use an offline record for a small set of comparable tasks. Track accepted outcomes, intervention, reviewer time, and rework by task type. Keep unresolved outcomes visible in the denominator.

Usage status is proposed. No independent validation or experiment was performed.

## Related note

- [Reading note on the preceding report](2026-10-21-openai-research-acceleration.md)

## Sources

- [OpenAI's public report](https://openai.com/index/research-acceleration-jagged-frontier/)
- [Task success and methods](https://openai.com/index/research-acceleration-jagged-frontier/#tasks-delegated-to-models-and-success-rates)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
