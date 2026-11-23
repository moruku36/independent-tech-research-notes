**English** | [日本語](2026-anthropic-enterprise-coding-agent-security.ja.md)

# Anthropic’s enterprise guide to securing coding agents

## Overview

- **What it is**: Anthropic’s deployment guide for securing enterprise coding agents, centered on Claude Code.
- **What it says**: It combines model-level judgment, externally enforced boundaries, and centrally managed policy.
- **Caveat**: The published evaluations and control availability depend on the tested versions, modes, and deployment.

## Practical reading (six lines)

- An agent’s access matters because its actions can use the permissions of the developer or process running it.
- Use scoped credentials, restrict file and network access, and keep audit evidence for actions and changes.
- Model training and classifiers provide one layer. Rules, isolation and pre-action checks enforce additional limits.
- Keep human approval for high-impact actions and verify which policies an administrator actually enforces.
- The guide cites zero successes in 720 attempts in an Anthropic-funded July evaluation of Claude Code auto mode under its specified settings.
- Proposed use: map approved access, high-impact actions, and audit evidence for a single pilot repository.

## Source and reading scope

Anthropic, November 23, 2026. Checked the original guide on November 24, 2026 JST, including judgment, boundaries, and managed policy. The cited tests and customer outcomes were not independently reproduced.

## Evidence and limitations

- **Controls.** The guide treats credential exposure, broad privileges, dependencies and prompt injection as distinct risks. It describes short-lived task credentials, filesystem and network restrictions, approval for high-impact actions, and session telemetry.
- **Coverage.** Classification is probabilistic. The guide describes settings an administrator can enforce and exceptions that depend on deployment and mode. Reading permissions, credentials, and network policy should be checked separately for local and cloud sessions.
- **Evidence.** The funded study used 72 indirect-injection scenarios with ten attempts each and agent versions available by July 17, 2026. The zero out of 720 is a result for those conditions. It does not establish a general rate of successful attacks.

## Application and free check

Proposed. Use a fictional repository and mock credentials to map which actions are permitted, blocked or require approval. Check that the final state and audit record independently reflect the intended policy.

## Related note

- [MCP controls across architectural layers](2026-mcp-security-three-tier-mitigation.md)

## Sources

- [Anthropic guide](https://claude.com/resources/articles/enterprise-guide-to-securing-coding-agents)
- [Requested Japanese page](https://claude.com/ja/resources/articles/enterprise-guide-to-securing-coding-agents)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
