**English** | [日本語](2026-google-cloud-envoy-agentic-stack.ja.md)

# Envoy for agent traffic: token budgets, model routing, and MCP

## Overview

- **What it is**: Google Cloud describes an Envoy-based architecture for model requests and agent tool traffic.
- **What it says**: It combines provider-format translation, estimates and accounting for tokens, cache-aware endpoint selection, and policy checks for tool traffic.
- **Caveat**: The article describes an ecosystem of components. Availability and effectiveness depend on the deployed proxy, extensions, backends, and policies.

## Practical reading (six lines)

- Provider requests can be normalized at the gateway, and streamed usage can contribute to token accounting.
- An admission estimate can limit work before inference, while usage reported by backends can inform later quota decisions.
- An Endpoint Picker can favor a model replica that has cached a matching prefix.
- The July 2026 MCP specification supports header-based dispatch. A stateless transport does not establish what a caller may do.
- Envoy can consult an external processor. The chosen policy and behavior on processor failure matter for sensitive operations.
- Proposed use: on a mock service, check quotas, model routing, and what happens if the policy service is unavailable.

## Source and reading scope

Abhi Maras and Boteng Yao, Google Cloud Blog, November 18, 2026. Checked November 23, 2026 JST against the Kubernetes Inference Extension overview, MCP release description, and Envoy external processing reference. No versions were deployed and no latency or policy-effectiveness measurements were reproduced.

## Evidence and limitations

- **Token accounting and routing.** The article distinguishes pre-inference estimates from usage reported in responses. Its quota and session examples depend on which counters and usage reports are available. Kubernetes documents endpoint selection as a distinct component that can account for prefix cache status. Cache locality and application state need separate handling.
- **MCP transport and policy.** The July 2026 release documents stateless request handling and routing metadata in HTTP headers. Tool authorization and consistency checks still require enforcement. Envoy’s external processing interface delegates checks and allows different behavior when the external service fails.
- **Evidence boundary.** The article discusses integrations and possible gains in throughput, latency and utilization. It does not present a matched performance or security evaluation of the full stack. Support and behavior should be checked for the specific versions in use.

## Application and free check

Proposed. Use a mock model backend and a mock read-only tool. Compare estimated and recorded usage, check whether a shared prefix changes routing, and document what a denied request or unavailable policy service returns. Track latency separately from the policy result.

## Related notes

- [RIVET multi-turn routing](2026-rivet-multiturn-llm-routing.md)
- [MCP control ownership](../security-governance/2026-mcp-security-three-tier-mitigation.md)

## Sources

- [Google Cloud article](https://cloud.google.com/blog/products/networking/the-envoy-agentic-stack-routing-models-tokens-and-mcp)
- [Kubernetes Inference Extension](https://gateway-api-inference-extension.sigs.k8s.io/)
- [MCP July 2026 specification announcement](https://blog.modelcontextprotocol.io/posts/2026-07-28/)
- [Envoy external processing reference](https://www.envoyproxy.io/docs/envoy/latest/api-v3/extensions/filters/http/ext_proc/v3/ext_proc.proto.html)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
