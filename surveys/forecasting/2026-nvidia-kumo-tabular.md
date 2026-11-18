**English** | [日本語](2026-nvidia-kumo-tabular.ja.md)

# NVIDIA Kumo Tabular: accuracy and inference cost for tabular prediction

## Overview

- **What it is**: An arXiv technical report on a family of tabular foundation models for classification and regression.
- **What it says**: Synthetic-only pretraining yields a model family whose largest variant ranks first by point estimate on eight benchmarks.
- **Caveat**: The lead varies by benchmark and split, with weaker rankings on held-out groups and very large contexts.

## Practical reading (six lines)

- The question is how far one pretrained model can generalize across new tables while keeping prediction affordable.
- A table encoder embeds rows, and an in-context transformer predicts from labeled examples without updating the weights for each dataset.
- On TabArena, the L model's accuracy is close to LimiX-2, while its measured prediction time is about one thirty-sixth as long.
- For recurring business predictions, test the small model against the current tree baseline on identical held-out groups.
- Measure context preparation, prediction latency and peak memory separately.
- Treat the benchmark rankings as conditional on the dataset, split and evaluation protocol.

## Source and reading scope

Jingang Qu et al., *NVIDIA Kumo Tabular: Pushing the Accuracy–Efficiency Frontier for Tabular Prediction*, arXiv:2611.23001v1, submitted November 17, 2026. Checked November 19, 2026 JST. Partial reading of the primary report covered the method, benchmark protocol and results, cost measurement, and limitations. Also checked the official code landing page and model card. Independent replication was not checked.

## Evidence and limitations

- **Predictive quality (§6, Tables 3–4).** All six Elo leaderboards show overlapping 95% intervals between Kumo Tabular-L and the highest-ranked non-Kumo entry. On TabArena v0.1.9.8 (October 19, 2026 snapshot), L scores 1962 Elo to LimiX-2's 1952, with a 49% head-to-head win rate across splits.
- **Timing (§6.1, §8).** The TabArena ratio uses median test-row prediction time per 1,000 rows on matched NVIDIA RTX PRO 6000 GPUs. Preparing the labeled context is measured separately. The H100 scaling study uses a different setup, including synthetic numeric inputs and an 80 GB GPU.
- **Generalization (§9).** On BeyondArena, L ranks fourth on grouped splits and ninth on tables with over 100,000 training rows. Pretraining used independent, identically distributed tables capped at 60,000 rows. The authors used subsets of TabArena, BeyondArena and TALENT for validation during development.
- **Release.** The code is Apache-2.0. The weights use OpenMDW-1.1.

## Application and free check

Proposed and untried. Use a small public dataset with meaningful groups, such as sales grouped by store. Compare Kumo Tabular-S and LightGBM locally with the same group splits and features, and tune the baseline within the training partition. Record split-level error and preprocessing, context preparation or fitting, prediction time and peak memory on the same hardware. If the workload is time-ordered, use a separate chronological holdout.

Usage status: proposed. No inference or replication runs were performed.

## Sources

- [Primary report, arXiv v1](https://arxiv.org/html/2611.23001v1)
- [NVIDIA code repository](https://github.com/NVIDIA/structured-data-models)
- [NVIDIA weights and model card](https://huggingface.co/nvidia/Kumo-Tabular)

[Theme index](README.md) · [Reading list](../../docs/reading-list.md)
