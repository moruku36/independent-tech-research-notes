**English** | [日本語](2026-shattered-self-hosted-llm-vs-api.ja.md)

# Shattered on self-hosted LLM and API costs

## Overview

- **What it is** Editorial comparison of hosting model weights and buying metered API inference.
- **What it says** Compares Kimi K3.1 Pro, GLM-5.3, DeepSeek V4.1 Flash and Mistral Large 4 through prices, memory requirements and operating assumptions.
- **Caveat** The break-even examples depend on an illustrative cluster cost and token mix.

## Practical reading (six lines)

- The article asks when the API bill exceeds the cost of running a cluster.
- It combines vendor documentation with an assumed five-to-one ratio of input to output tokens and zero cache hits.
- Total weight size informs memory sizing, while active parameters explain only part of throughput.
- API prices, checkpoint terms and runtime support need to be tied to the exact product and date.
- A proposed comparison uses cost per accepted result alongside monthly throughput and latency.
- The article combines benchmarks from different sources. Comparative quality remains uncertain.

## Source and reading scope

Tom Vance, Shattered, updated 2026-11-10. Checked 2026-11-11 JST. Partially read the comparison tables, price and break-even sections. Checked the Kimi architecture against Moonshot’s model card.

## Method, evidence and limitations

The article assumes a $30,000 monthly cluster cost in its illustrative table. For a fixed all-in monthly bill, cost parity is that bill divided by the blended API rate. Check separately whether measured throughput at realistic utilization and the required latency can serve that volume. The article’s additional utilization factor needs its own cost or capacity interpretation. Its price comparisons use a dated snapshot and DeepSeek’s displayed rates were unresolved in the article.

## Related work

- [Agent cache engineering](2026-cache-engineering-for-agents.md)
- [Emergent on Kimi K3.1 Pro](../articles/2026-emergent-kimi-k31-pro.md)

## Free check and usage status

Proposed, untried. Use a spreadsheet and synthetic counts for uncached input, cached input and output. Sweep cache hit rate and token mix, then compare modeled parity volume against serving capacity. Next check exact rate cards, checkpoint license, and an equal-quality workload before drawing deployment conclusions.

## Sources

- [Shattered article](https://shattered.io/self-hosted-llm-vs-api-kimi-k3-1-pro-glm-5-3-deepseek-v4-1-mistral-large-4-2026/)
- [Moonshot model card](https://huggingface.co/moonshotai/Kimi-K3.1-Pro)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
