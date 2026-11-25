**English** | [日本語](2026-google-cloud-enterprise-agent-controls.ja.md)

# Google Workspace and Cloud controls for enterprise agents

## Overview

- Google's announcement on managing agent access to Workspace data and Cloud tools.
- Workspace MCP and the CLI are generally available. Cloud Agent Gateway puts identity, access policy and optional inspections in the request path.
- Availability and enforcement vary by surface, deployment and date. The source describes product behavior without independently measured protection rates.

## Six practical takeaways

- Workspace offers managed MCP servers and a CLI with dedicated agent OAuth clients, scope limits, and access checks.
- Workspace handles high-impact actions such as email sending or Drive sharing changes through user confirmations. Administrators can audit and revoke agent access.
- The new addendum and technical enforcement start February 1, 2027. The developer guide describes how direct REST calls are limited and how Scaled Tier billing starts April 1.
- Workspace terms limit processing to authorized tasks and restrict training, retention and use of derived information. Disconnecting an integration also triggers data deletion obligations.
- On Cloud, Agent Gateway mediates agent traffic with IAM and outbound controls. Model Armor screening and other extensions depend on deployment and configuration.
- Proposed use. Evaluate a rollout with benign actions covering scopes, confirmation, logs, revocation and data cleanup.

## Publication and review scope

Chandu Thota and Brad Calder, Google Cloud Blog, November 24, 2026. Reviewed the announcement, Workspace terms, developer schedule and Gateway documentation on November 26, 2026 JST.

## Evidence and limitations

- The Workspace announcement distinguishes features shipping now from time-limited approvals, self-service activity review and data access restrictions described as forthcoming. OAuth scopes, DLP and classification labels provide different checks.
- February 1 is the scheduled addendum and MCP-enforcement date. The developer guide says direct agent REST calls receive Standard Tier limits, while the terms separately require Google MCP for covered use. April 1 is the billing and quota enforcement date. The Cloud gateway has separate deployment scopes, including limited preview on Cloud Run and cross-cloud Kubernetes.
- Gateway policy covers traffic routed through it. Enforcement of egress policies and payload screening depends on the gateway mode and enabled features. Put sensitive actions behind explicit authorization and keep independent audit evidence.

## Application and low-cost check

Proposed and untried. Map one synthetic document-reading workflow and one sensitive action to identity, scope, egress destination, approval, audit record and deletion owner. Review allowed and denied cases and assumptions about revocation.

## Related notes

- [MCP controls by layer](2026-mcp-security-three-tier-mitigation.md)
- [Enterprise coding-agent security](2026-anthropic-enterprise-coding-agent-security.md)

## Sources

- [Google Cloud announcement](https://cloud.google.com/blog/products/identity-security/deploying-agents-safely-in-your-enterprise)
- [Workspace announcement](https://workspace.google.com/blog/product-announcements/built-for-trust-and-control-new-ai-agent-protections-and-developer-tools-in-google-workspace)
- [Workspace AI Tools Addendum](https://workspace.google.com/terms/ai-tools/)
- [Workspace quota and rollout schedule](https://developers.google.com/workspace/guides/quota-usage-tiers?hl=en)
- [Agent Gateway documentation](https://docs.cloud.google.com/gemini-enterprise-agent-platform/govern/gateways/agent-gateway-overview)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
