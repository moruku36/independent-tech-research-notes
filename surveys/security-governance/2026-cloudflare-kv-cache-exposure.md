**English** | [日本語](2026-cloudflare-kv-cache-exposure.ja.md)

# Cloudflare’s GLM-5.3 KV-cache incident and remediation

## Overview

- **What it is** Cloudflare’s report of cross-request data exposure in one Workers AI model.
- **What it says** It reports 155 affected GLM-5.3 responses during August 27–September 9, 2026, followed by remediation.
- **Caveat** Scope and remediation are the provider’s findings. Independent verification is unperformed.

## Practical reading (seven lines)

- The incident concerns request isolation in the inference runtime.
- Insufficient KV capacity combined with incorrect rejection handling.
- The handoff allowed decode to use stale request state.
- Remediation addressed both configuration and engine behavior.
- Further work strengthens page lifetimes and transfer integrity.
- A proposed harness review records ownership and rejection paths alongside performance.
- Some integrity features remained under development or had limited model support.

## Source and reading scope

Kevin Flansburg and Michelle Chen, Cloudflare Blog, 2026-10-26. Checked 2026-11-12 JST. Selected incident, timeline and hardening sections read.

## Cause, remediation and evidence scope

The provider attributes the incident to mismatched capacity and error propagation across prefill/decode. It reports service restoration on September 9 and found no evidence of deliberate exploitation. Affected responses and affected customers are distinct counts. Its longer-term integrity prototype had reliability limitations.

## Related notes

- [KV cache engineering](../llm-infrastructure/2026-cache-engineering-for-agents.md)
- [TPU Sync](../llm-infrastructure/2026-google-tpu-sync.md)

## Free check and usage status

Proposed, untried. Diagram ownership, handoff, cancellation and release states for a synthetic two-request cache. Check that every failure reaches an explicit terminal state. Next inspect deployed build identifiers, model support and test evidence before assessing a particular installation.

## Primary source

- [Cloudflare incident report](https://blog.cloudflare.com/kv-cache-exposure-remediation/)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
