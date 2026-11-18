**English** | [日本語](2026-nemotron-labs-sigma-continuous-diffusion.ja.md)

# Nemotron-Labs-Sigma: continuous diffusion and decoding throughput

## Overview

- **What it is**: A preprint on 3B and 8B language models with blockwise continuous diffusion.
- **What it says**: Distillation reduces denoising calls, and a shared autoregressive stream can verify drafts to increase throughput.
- **Caveat**: Tokens per forward pass and measured tokens per second describe different experiments.

## Practical reading (six lines)

- The question is whether language models can generate useful blocks with fewer sequential calls.
- Sigma denoises 16-dimensional token embeddings and shares a backbone with an autoregressive stream initialized from pretrained weights.
- Distribution-matching distillation improves quality at low step budgets on selected math and coding tasks.
- Self-speculative decoding uses one diffusion draft and an autoregressive verifier that keeps the matching greedy prefix.
- For serving evaluation, compare the same checkpoint on the same prompts and hardware in both modes.
- Report throughput, latency, and answer quality together, including prompts that repeat or hit the length cap.

## Source and reading scope

Zhihan Yang et al., *Large Language Continuous Diffusion Models*, arXiv:2610.02665v2, revised November 12, 2026. Checked November 19, 2026 JST. Partially read the primary report, including §§3–7 and selected results in Appendix H, and checked the official weights collection. Independent replication was not checked.

## Evidence and limitations

- **Few-step generation (§5.2).** The headline 8 and 4 tokens per forward pass for selected math and coding settings are model-call efficiency figures. At eight denoiser evaluations per block (four tokens per forward pass), the distilled models roughly match the strongest 256-step Sigma sampler on GSM8K and HumanEval. The paper notes more syntax errors at low step counts on MBPP.
- **Serving (§6, Appendix H, Tables 22–23).** Before instruction tuning, Sigma-distill-8B records 3.92× on GSM8K, 2.37× on HumanEval, and 3.26× on MBPP against its own greedy autoregressive mode. The authors measure client-side answer tokens per second with SGLang, BF16, and one request at a time on a GB200. Timing excludes looping and length-capped outputs. On HumanEval the masked NLD-8B baseline still delivers more absolute speculative tokens per second (652 vs. 543).
- **Quality (§§4.4, 7).** Instruction-tuned scores vary by benchmark and decoding settings. Pass@k measures whether additional attempts find a correct solution. It is an indirect indicator of useful diversity.

## Application and free check

Proposed and untried. Start offline by recalculating the speedup ratios in Table 22 and listing the kept-prompt counts from Table 23. If the implementation and hardware are available later, compare both decoding modes with the same checkpoint, prompts, and stop rules. Record answer agreement, request latency, output throughput, and timeout or cap rates before testing concurrent requests.

Usage status is proposed. No inference or replication runs were performed.

## Sources

- [Primary report, arXiv v2](https://arxiv.org/html/2610.02665v2)
- [NVIDIA model weights collection](https://huggingface.co/collections/nvidia/nemotron-labs-sigma)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
