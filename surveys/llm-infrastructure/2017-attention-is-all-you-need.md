**English** | [日本語](2017-attention-is-all-you-need.ja.md)

# Attention Is All You Need: the original Transformer

## Overview

- **What it is** The NeurIPS 2017 paper introducing the Transformer for sequence transduction.
- **What it says** Attention connects positions directly and allows training computation across positions to be parallelized.
- **Caveat** The translation results are historical, and the arXiv and proceedings versions differ on one reported score.

## Practical reading (six lines)

- The original architecture is an encoder–decoder with attention and position-wise feed-forward layers.
- Scaled query–key dot products set the weights on values. Multiple heads use different learned projections.
- Positional encodings supply order information, and causal masking hides later target positions.
- Training can process target positions in parallel with the target sequence supplied. Inference still emits tokens autoregressively.
- Full self-attention has a per-layer cost of O(n²d) for sequence length n and representation width d.
- On WMT 2014 English–German, Transformer (big) scored 28.4 BLEU after 3.5 days of training on eight P100 GPUs.

## Source and reading scope

Ashish Vaswani et al., *Attention Is All You Need*, NeurIPS 2017. First submitted June 12, 2017. On November 20, 2026 JST, checked arXiv v7 (August 2, 2023), including the architecture, complexity, and translation results, and compared the proceedings result.

## Evidence and limitations

- **Architecture (§§3–4).** The encoder uses self-attention. The decoder combines masked self-attention with attention to encoder outputs. Parallelism across positions trades against quadratic sequence-length cost in full self-attention.
- **Translation (§§5.2, 6.1 and Table 2).** The authors compare WMT 2014 results against then-published systems. For English–French, the v7 abstract and Table 2 give 41.8 BLEU. Its §6.1 and the NeurIPS proceedings abstract, §6.1 and Table 2 give 41.0. The sources examined leave the discrepancy unexplained.

## Application and free check

Proposed and untried. Use a small CPU example to compute attention weights and verify that changing later tokens leaves an earlier masked output unaffected. Track score-matrix size at two sequence lengths. No training or benchmark replication was performed.

## Related note

- [DLite and speculative decoding](2026-dlite-history-free-speculation.md)

## Sources

- [arXiv v7 full text](https://arxiv.org/html/1706.03762v7)
- [NeurIPS 2017 proceedings PDF](https://proceedings.neurips.cc/paper_files/paper/2017/file/3f5ee243547dee91fbd053c1c4a845aa-Paper.pdf)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
