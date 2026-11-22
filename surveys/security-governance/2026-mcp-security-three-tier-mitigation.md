**English** | [日本語](2026-mcp-security-three-tier-mitigation.ja.md)

# MCP security controls across server, gateway, and protocol

## Overview

- **What it is**: Krakauer and Schaad’s framework maps MCP security responsibilities across three architectural layers.
- **What it says**: Table 1 assigns five of ten OWASP MCP categories to the server, two to the gateway, and three to the protocol as their primary layer.
- **Caveat**: The confidence labels are qualitative judgments informed by one Go file-transfer server case.

## Practical reading (six lines)

- The authors use four questions to identify where a control can be enforced and what evidence supports it.
- Identity and permission controls have a clear server-side owner in the map.
- A gateway can enforce policy across connected services and give operators a common place to review activity.
- The paper identifies a protocol-level limit when external data and instructions enter the same model context.
- The study checks a single Go managed file transfer server. Its High, Medium, and Low categories give no measured failure probabilities.
- Proposed use: assign a control owner at each layer and record what happens when approval or authorization cannot be verified.

## Source and reading scope

Christopher Krakauer and Andreas Schaad, *Where Does MCP Security End? A Three-Tier Mitigation Mapping Framework for the OWASP MCP Top 10*, arXiv v1, November 2, 2026. Checked November 23, 2026 JST, focusing on Sections 5–7 and Table 1. No independent server testing was performed.

## Evidence and limitations

- **Mapping.** Each category gets a primary layer, with other layers available for partial protection. Table 1 has three High, four Medium, and three Low assignments. All three Low assignments are protocol-primary in the authors’ mapping.
- **Case study.** The authors report that deterministic server controls behaved as expected in the managed file transfer implementation, while model-mediated risks retained limits at other layers. The participant-observer design, one SDK and deployment, and qualitative assessment constrain generalization.
- **Operational implication.** Treat an MCP routing decision, caller authorization, and the model’s interpretation of returned content as distinct checks. The paper’s classification is the authors’ analytical framework and is separate from the OWASP taxonomy it uses.

## Application and free check

Proposed. In a fictional file service, make an ownership table for identity, permission to access a document, approval for edits, and audit evidence. For a few allowed and denied mock actions, check on paper which component enforces the rule and how missing authorization is handled.

## Related notes

- [OWASP’s agentic application risk taxonomy](2025-owasp-agentic-top10.md)
- [Envoy’s agent traffic architecture](../llm-infrastructure/2026-google-cloud-envoy-agentic-stack.md)

## Sources

- [arXiv record](https://arxiv.org/abs/2611.02611)
- [Paper PDF](https://arxiv.org/pdf/2611.02611)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
