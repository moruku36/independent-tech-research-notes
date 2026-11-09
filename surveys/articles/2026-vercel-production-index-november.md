**English** | [日本語](2026-vercel-production-index-november.ja.md)

# Vercel Production Index: requests, adoption and spend differ

## Overview

- **What it is**: A report on one gateway's aggregate production traffic.
- **What it says**: Decision-model request share differs sharply from spend share.
- **Caveat**: Gateway customers are not a representative global market sample.

## Practical reading (six lines)

- Request volume does not equal revenue or capability.
- The report records decision-model adoption and model switching.
- Spend uses list-price estimates rather than actual bills.
- Our proposal: separate routing decisions from text generation.
- Free check: define denominators before comparing providers.
- Do not infer causal superiority from adoption trends.

## Bibliography and verification scope

Amelia Charles and Harpreet Arora, Vercel, 2026-11-09; corporate traffic report through October 2026.

Checked 2026-11-10 JST. Primary article returned by search checked, including About this data; direct open failed. Raw data and separate methodology were not analyzed.
Status: primary source checked / partially read / not reproduced.

## Question, method, claims and evidence

It reports decision models at 26% of October requests but 0.53% of spend. A new team's first-choice lab means its largest language-model request share in its first month. Paid-team, token-volume and model-version definitions matter.

## Comparison with related work

RIVET studies routing decisions; this report describes observed usage, not their causal effectiveness. [Related note](../llm-infrastructure/2026-rivet-multiturn-llm-routing.md)

## Free check plan, usage status and next checks

For harness routing, evaluate task accuracy, latency and total cost on the same workload instead of copying gateway popularity. Free check: make a synthetic accounting table with requests, tokens, spend and teams as separate columns. Proposed only. Next: inspect raw downloadable data and revision methodology.

## Primary sources

- [Requested source](https://vercel.com/blog/ai-gateway-production-index-november-2026)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
