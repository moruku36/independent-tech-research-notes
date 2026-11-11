**English** | [日本語](2026-qwen4-max-preview.ja.md)

# Qwen4-Max-Preview access and output-budget semantics

## Overview

- **What it is** Alibaba Cloud documentation for qwen4-max-preview.
- **What it says** It specifies multimodal input, reasoning, tool calling and a time-limited Token Plan preview.
- **Caveat** These are provider specifications. Independent capability and compatibility tests have yet to be performed.

## Practical reading (six lines)

- The page supports text, image and video input with text output.
- It lists a 1M-token context and 393,216 output tokens shared by reasoning and the final answer.
- For Chat Completions, max_tokens limits that combined output budget.
- Access is through Token Plan with a dedicated endpoint.
- The documented preview ends November 25 at 24:00 UTC+8, followed by retirement.
- A proposed adapter test checks truncation, structured output and tool results on fixed synthetic inputs.

## Source and reading scope

Alibaba Cloud Model Studio. Updated 2026-11-11, checked 2026-11-12 JST. Read capabilities, specifications, access conditions and usage notes. API calls were not made.

## Method, evidence and limitations

The documentation lists Chat Completions, Responses and Anthropic Messages compatibility. Actual parameter and tool behavior needs protocol-specific checks. The listed context capacity is a specification, while retrieval accuracy and workload latency require measurement.

## Related notes

- [Kimi K3.1 Pro release](2026-emergent-kimi-k31-pro.md)

## Free check and usage status

Proposed, untried. Prepare fixtures for JSON validation, a harmless tool response and a long-input question. Record the expected outputs and a comparable token budget. Next check availability and replacement model documentation after the preview.

## Primary sources

- [Model documentation](https://www.alibabacloud.com/help/en/model-studio/qwen4-max-preview)
- [API compatibility changes](https://www.alibabacloud.com/help/en/model-studio/api-compatibility-upgrade-notice)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
