**English** | [日本語](2025-tool-invocation-coding-agent-redteam.ja.md)

# Red-teaming coding agents through tool invocation

## Overview
- **What it is:** A preprint assessing tool-invocation security across six coding agents.
- **What it reports:** Under an attacker-controlled external-tool assumption, the authors test internal-prompt leakage and tool-call hijacking.
- **Caveat:** The arXiv abstract's claim of success on every tested pair conflicts with zero-success entries in the HTML results table.

## Source and scope
Yuchong Xie, Mingyu Luo, Zesen Liu, Zhixiang Zhang, Kaikai Zhang, Yu Liu, Zongjie Li, Ping Chen, Shuai Wang and Dongdong She, [Red-Teaming Coding Agents from a Tool-Invocation Perspective: An Empirical Security Assessment](https://arxiv.org/html/2509.05755v6), arXiv:2509.05755v6, revised 28 June 2026 (v1: 6 September 2025). Checked 3 November 2026 JST: selected primary HTML abstract, threat model, results table, defenses and validity discussion. PDF, attack code and current product state not checked; no reproduction.

## Question and method
Tool descriptions and returns normally supply task data. The authors assume an attacker can induce connection to an attacker-controlled external tool and control its description and return. They evaluate leakage of internal instructions and inducement of privileged built-in command execution; the attacker cannot directly change model weights or built-in tools. Six products and multiple model combinations are assessed.

## Results and unresolved discrepancy
The arXiv abstract reports leakage in 19 of 25 agent–model pairs and code execution on every tested pair. The HTML abstract and introduction report best pseudo-recall in 18/25 pairs, a different metric from whether any leakage occurred. In contrast, Table 5 includes **0/10** outcomes for the two-channel attack in several newer configurations, including the listed new Claude Code configurations. The broad arXiv abstract claim and the table do not reconcile on their face; a condition or version explanation was not verified. Each table cell represents ten trials; findings do not establish the safety of all current product versions.

## Proposed applications
Vet external MCP tools, provenance, updates and necessary permissions. Treat tool metadata and returns as untrusted input, isolate execution, limit secret access and egress, and require explicit approval and deterministic authorization for consequential actions. Test suspicious arguments and instructions in an authorized environment. These are proposals, not a guarantee of production protection.

## Limits
The results depend on the malicious external tool connection assumption, selected agents, backends, settings and small trial counts; the paper measures RCE through invocation of the intended command tool, which does not guarantee real-world impact under different OS or network restrictions; products can change. No independent validation, reproduction or adoption.

[AI agent safety index](README.md)
