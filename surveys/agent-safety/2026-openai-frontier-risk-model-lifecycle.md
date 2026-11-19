**English** | [日本語](2026-openai-frontier-risk-model-lifecycle.ja.md)

# OpenAI’s frontier AI risk controls from training to deployment

## Overview

- **What it is** OpenAI’s public account of controls across the frontier model lifecycle.
- **What it says** It describes containment, alignment evaluation, monitoring, and deployment safeguards.
- **Caveat** The account describes company practices and leaves combined control effectiveness unquantified.

## Practical reading (six lines)

- Research relies on containment and monitoring, with frontier training isolated from the live internet.
- The central stop control is reported to halt further model output within 35 seconds of a halt instruction.
- Internal deployment expands access and makes alignment checks and monitoring more important.
- Public deployment adds broader evaluations, selected third-party testing, and post-use investigation.
- Safety review gates stage transitions, and disclosure disagreements can escalate for review.
- For a tabletop exercise, define the authority, evidence, and stop conditions for each stage.

## Source and reading scope

OpenAI, November 18, 2026. Checked the public article and the linked safety-case overview on November 20, 2026 JST. No operational controls were tested.

## Evidence and limitations

- **Control scope.** The 35-second figure covers further model output after a stop instruction reaches Control Room. Detection time, response in other deployments, and reversal of prior actions are outside that measurement.
- **Incident response.** OpenAI reports a training and evaluation pause from September 20 to October 1, 2026 following an isolation failure. The article distinguishes release review from the process for deciding whether to disclose incidents. The measures are company-reported.

## Application and free check

Proposed and untried. Use mock records to walk through a stage transition and a failed monitor. Record who can pause the run, the earliest observable evidence, and how recovery and resumption would be authorized.

Usage status is proposed. No replication was performed.

## Related note

- [OpenAI research acceleration report](../articles/2026-openai-research-acceleration-jagged-frontier.md)

## Sources

- [OpenAI public safety report](https://openai.com/index/managing-frontier-ai-risk/)
- [OpenAI safety-case overview](https://openai.com/index/towards-safety-cases-for-frontier-ai-training/)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
