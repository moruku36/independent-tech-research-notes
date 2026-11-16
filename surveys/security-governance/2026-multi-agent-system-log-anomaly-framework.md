**English** | [日本語](2026-multi-agent-system-log-anomaly-framework.ja.md)

# Multi-agent log analysis: evidence checks versus confidence scores

## Overview

- **What it is**: A paper describing a Gemini/n8n workflow for system-log analysis.
- **What it says**: It separates parsing, domain analysis, evidence checking and reporting.
- **Caveat**: Sixteen demonstrations and model confidence scores do not establish detection accuracy.

## Practical reading (7 lines)

- The question is whether role-separated analysis can retain log evidence through a workflow.
- The design describes seven layers and eight named agents, with parallel formatters and domain routing.
- Gemini 2.0/2.5 Flash supports analysis; a guard checks quotations and confidence rules.
- Results present three examples and thirteen additional cases, not a controlled detector benchmark.
- Proposed use: require every finding to cite retained log lines and distinguish observation from inference.
- Proposed evaluation: check evidence deterministically and measure false alarms on labeled normal logs.
- A confidence cap is a policy rule, not calibrated probability or measured accuracy.

## Bibliography and reading scope

Ngoc-Son Le, Huy-Hoang Mac Nguyen, Ngoc Hong Tran. *An Agentic Multi-Agent Framework for System Log Anomaly Detection*. arXiv:2611.10612v1, 2026-11-07.

Checked 2026-11-17 JST. Primary PDF methodology, implementation, results and Table 2 text checked (18 PDF pages); figure screenshots not exhaustively inspected. Partial reading / not reproduced. arXiv lists publication at ICMR 2026, pp. 63–80, ISBN 978-974-474-120-2; proceedings independently unverified.

- [arXiv record and version history](https://arxiv.org/abs/2611.10612v1)
- [Inspected full text](https://arxiv.org/pdf/2611.10612v1)
- [DOI](https://doi.org/10.48550/arXiv.2611.10612)

## Method, evidence and limitations

No confusion matrix, independent ground-truth audit, controlled SIEM/single-agent comparison or quantified latency/cost benchmark is supplied in the inspected results. Table 2 includes 100% confidence despite the described caps; application of those rules needs checking. Anomaly flags, severity and confidence are distinct fields. Verbatim evidence supports traceability, not the truth of causal interpretation.

## Comparison with related notes

[BEACON](../cloud-resilience/2026-beacon-cloud-anomaly-detection.md) evaluates a detector with a specified scoring protocol. This workflow emphasizes explanation and evidence handling; its confidence values cannot be compared with BEACON's F1. See also [AI cloud-threat validation](2026-ai-cloud-threat-validation.md).

## Free-to-run check and usage status

Proposed, free and unrun: use invented, non-sensitive logs with known normal/error labels and stable line IDs. Hand-author reports with exact, altered and missing quotations; verify citations and schema without an LLM. Track precision, recall, false alarms, abstentions and evidence coverage independently. Before a live trial, define redaction, retention, untrusted-log handling, human review and token/cost limits; do not enable automatic remediation. Next inspect workflow artifacts and reconcile confidence caps with reported outputs. No real logs or provider calls were used.

Usage status: proposed / untrialed / not adopted.

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
