**English** | [日本語](2025-deepcrossattention-transformer-residuals.ja.md)

# DeepCrossAttention: selecting features across transformer layers

## Overview

- **What it is**: A Google Research article and its ICML 2025 paper on changing how transformers carry information between layers.
- **What it says**: DeepCrossAttention (DCA) learns token-dependent mixtures of earlier layer outputs and uses distinct combinations for attention queries, keys, and values.
- **Caveat**: Time to a target perplexity, number of steps, and batches per second are distinct measures. The result depends on the model and the retained layer history.

## Practical reading (six lines)

- A standard residual stream adds layer contributions. DCA learns which earlier outputs to reuse for each token.
- On the 24-layer LM1B comparison, 2-DCA reached the baseline Transformer’s final perplexity in 0.33× the training time.
- That same variant ran at 5.39 batches per second versus 8.14 for the Transformer. It needed fewer steps to reach the target.
- The blog reports up to 5× fewer steps to reach baseline levels in the language-modeling experiments.
- For a six-layer LM1B model, 60,000 extra steps lowered perplexity by 0.19 after retrofitting DCA and by 0.02 under standard continuation.
- Proposed use: track time and steps to the same loss along with throughput, peak memory, and inference latency.

## Source and reading scope

Kyriakos Axiotis and Thomas Fu, Google Research, November 23, 2026. The companion ICML 2025 paper is by Mike Heddes, Adel Javanmard, Kyriakos Axiotis, Gang Fu, Mohammadhossein Bateni and Vahab Mirrokni. Checked November 25, 2026 JST, including arXiv:2502.06785v2 Tables 1 and 4. No training or inference runs were reproduced.

## Evidence and limitations

- **Mechanism.** The learned mixture depends on both the layer and token. Attention’s query, key, and value inputs can combine depth history differently. This concerns reuse across layers, alongside the existing mechanism for attention across the sequence.
- **Training evidence.** In Table 1, the 24-layer Transformer’s final LM1B perplexity was 15.14. The 2-DCA variant reached that target in a third of the time and finished at 14.41. In Table 4, a pretrained six-layer baseline starts at 18.98. After 60,000 additional steps the baseline reached 18.96 and the DCA retrofit reached 18.79.
- **Trade-offs.** Parameter overhead can be small while retaining and reading outputs from earlier layers still increases memory traffic. The study varies the number of retained outputs and reports inference latency for specific variants. Its training-time improvement does not establish an inference-speed gain over the standard Transformer.

## Application and free check

Proposed. Compare small, matched models on a public dataset. Hold tokenizer, context length and target loss fixed. Log batches per second, time and updates to target loss, peak training memory, and inference latency.

## Related notes

- [The original Transformer](2017-attention-is-all-you-need.md)
- [Inkling 2 Mini and repeated layer computation](2026-thinking-machines-inkling-2-mini.md)

## Sources

- [Google Research overview](https://research.google/blog/supercharging-transformer-residual-connections/)
- [ICML 2025 proceedings](https://proceedings.mlr.press/v267/heddes25a.html)
- [arXiv v2 tables and methods](https://arxiv.org/html/2502.06785v2)

[Theme index](README.md) | [Reading list](../../docs/reading-list.md)
