**English** | [日本語](2026-aws-api-ai-security-discovery-protection.ja.md)

# AWS API and AI security: discovery, managed rules, and coverage

## Overview

- AWS announced general availability of API Portal discovery and the AWS WAF API Security and AI Security managed rule groups.
- API Portal inventories endpoints while the two rule groups inspect traffic on associated AWS resources.
- Application authorization, supported resources and regions, inspection limits, and guardrail failure behavior remain part of the deployment design.

## Six practical takeaways

- API Portal builds inventory from traffic and configuration across supported CloudFront distributions, Application Load Balancers, and API Gateway REST APIs.
- Discovery can run for one account or an AWS organization. The inventory can surface LLM inference, MCP and A2A endpoints alongside other APIs.
- API Security checks individual requests and learns patterns from API traffic. Behavioral actions vary by confidence.
- An API still needs its own token validation and object-level authorization. WAF observes requests and behavior at its inspection point.
- AI Security recognizes agent protocols and can call Amazon Bedrock Guardrails for content checks. Response inspection requires enablement and has a body size limit.
- The default allows traffic through when a Guardrails call fails and adds a label. Account for that behavior in monitoring and availability decisions.

## Publication and review scope

AWS Security Blog, November 23, 2026. Reviewed the English launch and AWS developer guides on November 25, 2026 JST. This note is based on public materials.

## Evidence and limitations

- Discovery uses entry-point logs and configuration and can be scoped across AWS Organizations. Inventory and WAF protection can be compared per endpoint, with coverage bound to supported resources and web ACL associations.
- API Security analyzes request structure and traffic patterns, including application response status codes. The application owns signature validation and access decisions for specific objects.
- AI Security evaluates supported MCP and A2A versions for protocol compliance. Bedrock Guardrails content checks depend on workload type, traffic direction, and supported Regions. The launch explains defaults and examples and does not supply independently measured detection or false-positive rates.

## Application and low-cost check

Use a staging inventory of owned endpoints to compare entries with web ACL associations. Inspect labels, response inspection coverage, and normal request volume and error rates before broadening enforcement.

## Related notes

- [MCP controls across server, gateway, and protocol](2026-mcp-security-three-tier-mitigation.md)
- [Enterprise protections for coding agents](2026-anthropic-enterprise-coding-agent-security.md)

## Sources

- [AWS Security Blog launch](https://aws.amazon.com/blogs/security/introducing-api-and-ai-security-on-aws-from-discovery-to-protection/)
- [API Portal developer guide](https://docs.aws.amazon.com/apigateway/latest/developerguide/apiportal.html)
- [AWS WAF API Security managed rules](https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-api-security.html)
- [AWS WAF AI Security managed rules](https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-ai-security.html)

[Topic index](README.md) | [Reading list](../../docs/reading-list.md)
