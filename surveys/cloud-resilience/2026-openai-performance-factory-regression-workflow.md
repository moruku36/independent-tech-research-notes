**English** | [日本語](2026-openai-performance-factory-regression-workflow.ja.md)

# OpenAI Performance Factory: investigating and verifying regressions

## Overview

- **What it is** An OpenAI engineering account of Codex-assisted performance operations.
- **What it says** Agents investigate alerts and validate recovery around engineer-reviewed changes.
- **Caveat** The published volumes cover investigations and root-cause findings.

## Practical reading (six lines)

- A performance alert opens a task with durable state and evidence.
- A dispatcher assigns ready steps, and subscriptions resume work after external events.
- A separate session challenges the first diagnosis against available evidence.
- An engineer decides what ships, and an agent checks recovery after deployment.
- In just over three months, OpenAI reports more than 1,700 investigations and more than 600 root-caused cases.
- Backtest diagnosis and handoff quality separately before changing the workflow.

## Source and reading scope

Okay Zed and Cyrus Forbes, OpenAI, November 19, 2026. Checked the architecture, regression workflow, and evaluation sections on November 20, 2026 JST.

## Evidence and limitations

Investigation counts and root-cause counts do not establish an independently audited accuracy or recovery rate. Historical investigations start from the original signal with known answers withheld. Telemetry expiry and evidence collected later can distort the backtest. The workflow scores timing, affected requests, and evidence for the proposed cause, and grades task summaries separately.

## Application and free check

Proposed and untried. Replay one synthetic slowdown offline. Provide only signals available at alert time, have a reviewer challenge the cause, and check recovery against a fixed baseline.

Usage status is proposed. No deployment or replication was performed.

## Related notes

- [Claude Code verification practices](../coding-agents/2026-claude-code-verification-practices.md)

## Sources

- [OpenAI engineering account](https://openai.com/index/how-openai-performance-factory-keeps-chatgpt-fast/)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
