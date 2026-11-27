**English** | [日本語](2026-jacopen-platform-engineering-agent-era.ja.md)

# Platform engineering for AI agents and accountable teams

## Overview

- Kazuto Kusama’s Architecture Conference 2026 talk on what an internal platform takes on when AI agents execute development work.
- The platform serves both agents that act and people who set policy and own the outcome. It connects them through interfaces, context, permissions, policy and accountability.
- The slides propose a design and rollout approach. They draw on external reports for motivation and identify a shortage of direct evidence.

## Six practical takeaways

- The talk distinguishes carrying out work, knowing local context, applying restraint, and taking responsibility for outcomes. It proposes giving both people and agents suitable ways to use the same platform.
- Keep a portal for people and offer CLI, API or MCP interfaces as appropriate. Apply the same underlying validation wherever the request enters.
- Expose service ownership, architecture decision records and acceptance criteria as context. Prefer versioned shared components and automatically refresh facts that can be derived from systems.
- Use dedicated agent identities and start with read access. Put binding checks in infrastructure and CI or delivery gates, with audit records for what ran.
- Keep people accountable for release decisions and incidents. The talk proposes reserving human approvals for high-impact or irreversible changes and using automated checks for lower-risk reversible changes.
- Proposed use. Pilot one well-understood delivery path and measure rework, errors and cost alongside lead time and rollback readiness.

## Publication and review scope

Kazuto Kusama (@jacopen), Architecture Conference 2026. Reviewed the 52 published slides on November 27, 2026 JST, focusing on slides 10–26 and 29–51. No implementation or operational validation.

## Evidence and limitations

- Slides 20–29 identify five design concerns and illustrate the common backend check. Service facts can come from systems, and people can record the rationale that those systems cannot infer. The deck also describes retaining a trace of intent, plan, execution and verification.
- Slides 31–41 distinguish permissions, binding policy and ownership. The talk assigns policy criteria to security teams, control implementation and logging to platform teams, and product scope, release approval and incident operations to application teams.
- Slides 43–50 propose moving safe defaults and local rules into shared services and component references. This depends on reliable tests, a readily available validation environment, and rehearsable deployment and rollback. The deck leaves the right amount of human approval and operational generalization open.

## Application and low-cost check

Proposed and untried. In a test environment, map a preview deployment through a portal and an agent interface. Check that both routes enforce the same policy and that audit records connect the requester, agent identity, checks and outcome. Compare rework, failures and cost before expanding scope.

## Related notes

- [Google Workspace and Cloud controls for enterprise agents](../security-governance/2026-google-cloud-enterprise-agent-controls.md)
- [Claude Code verification practices](2026-claude-code-verification-practices.md)

## Sources

- [Published slides on Speaker Deck](https://speakerdeck.com/jacopen/purattofomu-ha-dare-no-tame-ni-nani-o-hikiukeru-no-ka-ai-ejento-jidai-ni-toi-naosu-platform-engineering)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
