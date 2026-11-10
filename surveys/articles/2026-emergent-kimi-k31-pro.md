**English** | [日本語](2026-emergent-kimi-k31-pro.ja.md)

# Emergent on the Kimi K3.1 Pro weight release

## Overview

- **What it is** News coverage of Moonshot’s Kimi K3.1 Pro downloadable weights.
- **What it says** The model card lists 2.8T total parameters, 104B active parameters and a 1,048,576-token context.
- **Caveat** Benchmark scores come from the vendor and deployment results depend on runtime and workload.

## Practical reading (six lines)

- The release concerns downloadable weights for a multimodal mixture-of-experts model.
- Moonshot lists MXFP4 weights and MXFP8 activations after quantization-aware training.
- The article reports 65.7 on Terminal-Bench 4.0 from Moonshot’s evaluation.
- The context limit is an input capacity specification. Effective retrieval across the window needs its own evaluation.
- For an agent study, a proposed comparison varies where task evidence appears in the input.
- The checkpoint uses a named custom license. Check the license text for the intended use.

## Source and reading scope

Kyle Morrison, Emergent, 2026-11-05. Checked 2026-11-11 JST. Read the release article and checked architecture and benchmark entries in the Moonshot model card. Emergent dates the downloadable weight release to November 4.

## Method, evidence and limitations

The article relays vendor benchmarks with their own task configurations. Cross-model results depend on tool access, inference settings and scoring. The activated parameter count describes per-token routing. Serving also needs to account for total weights, context state and runtime overhead. The API offering and weight release have separate terms and dates.

## Related work

- [Self-hosted versus API cost comparison](../llm-infrastructure/2026-shattered-self-hosted-llm-vs-api.md)

## Free check and usage status

Proposed, untried. Make a small synthetic document set with cited answers and controlled evidence positions. Write expected answers and scores before choosing a runner. Compare retrieval, answer accuracy and latency under a fixed context budget. The task-design step requires no download or model calls. Next check benchmark configuration and deployment requirements.

## Sources

- [Emergent article](https://emergent.sh/news/moonshot-releases-kimi-k3-1-pro-2-8t-moe-1m)
- [Moonshot model card](https://huggingface.co/moonshotai/Kimi-K3.1-Pro)
- [Checkpoint license](https://huggingface.co/moonshotai/Kimi-K3.1-Pro/blob/main/LICENSE)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
