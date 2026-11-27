**English** | [日本語](2026-jan-lukas-else-ai-assisted-self-hosting.ja.md)

# AI-assisted self-hosting with versioned infrastructure

## Overview

- A first-person account by Jan-Lukas Else on using AI coding agents to work on personal infrastructure.
- Git-managed configuration and conventional automation made it easier for the author to try unfamiliar systems, ship small tools and keep services updated.
- The source reports one operator’s experience. Counterfactual time estimates and recurring benefits were not measured in a controlled comparison.

## Six practical takeaways

- The author manages Compose files, scripts and configuration in Git so coding agents can review and propose changes in context.
- AI assistance made the author more willing to experiment with NixOS at home and a Debian-based bootc image for VPS infrastructure.
- Renovate proposes dependency updates. GitHub Actions and Forgejo Actions handle builds and deployments after changes are pushed or merged.
- The same pipeline helped the author build and deploy small Go tools for personal needs.
- The reported benefit includes fewer barriers to trying ideas. The author still owns reviews and recurring maintenance as services accumulate.
- Proposed use. Take one low-risk service and compare setup effort and ongoing update and recovery effort before expanding.

## Publication and review scope

Jan-Lukas Else, “AI made self-hosting fun again,” November 26, 2026. Read the published account on November 28, 2026 JST. The described infrastructure was not inspected or reproduced.

## Evidence and limitations

- In this account, AI helped assemble existing infrastructure practices. Git, dependency PRs and CI workflows provide repeatability during later updates.
- The bootc setup reportedly took half a day with assistance. The estimate of at least a week without assistance is the author's counterfactual, so it does not establish a speedup ratio.
- Automating routine updates can reduce per-service effort, while more services increase what the operator must understand and support. The article does not report a long-term incident or maintenance rate.

## Application and low-cost check

Proposed and untried. In an isolated service, version the configuration, review an update, and confirm deployment and rollback. Record time spent on setup, review, and follow-up.

## Related notes

- [Platform engineering for AI agents](../coding-agents/2026-jacopen-platform-engineering-agent-era.md)
- [Self-hosted LLMs versus APIs](../llm-infrastructure/2026-shattered-self-hosted-llm-vs-api.md)

## Sources

- [Primary source](https://janlukas.blog/posts/ai-self-hosting)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
