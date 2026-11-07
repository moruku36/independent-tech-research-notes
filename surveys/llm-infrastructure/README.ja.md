**日本語** | [English](README.md)

# LLM推論基盤と費用対効果

LLM推論のハードウェア選択、スケジューリング、KVキャッシュ制御、長期記憶検索。

## 2026-11-07追加

- [AB-MCTS：新しい候補と既存案の改善を配分する探索](2025-sakana-adaptive-branching-mcts.ja.md) — 研究記事＋対応論文v5。探索方式を部分確認／Pass@250と最終解選択を区別／再現未実施。

- [LLMs in Cloud：アーキテクチャ・運用制御・推論の総説](2026-llms-cloud-architecture-orchestration-survey.ja.md) — 総説プレプリント。方法・主要議論を部分確認／文献選定の不一致を記録／引用性能は未検証。

## 2026-11-06追加

- [RIVET：複数ターンLLMルーティングの精度と費用](2026-rivet-multiturn-llm-routing.ja.md) — 一次資料の主要部分を確認。再現・独立検証は未実施。
- [NVIDIAのメモリー階層とフルスタック共同設計](2026-nvidia-memory-full-stack-codesign.ja.md) — 一次資料の主要部分を確認。再現・独立検証は未実施。

- [Demystifying Cost-Efficiency in LLM Serving over Heterogeneous GPUs](2025-heterogeneous-gpu-llm-serving.ja.md)（[arXiv:2502.00722](https://arxiv.org/abs/2502.00722)、v2、2025）— 6種類のGPUの計測と、価格予算のもとでGPU構成・配置・負荷割り当てを決めるMILPスケジューラ。部分読了（§4.2の途中まで）／会場未確認／再現未実施。

- [Cache Engineering for Agents](2026-cache-engineering-for-agents.ja.md)（[arXiv:2610.28577v1](https://arxiv.org/html/2610.28577v1)、2026）— エージェントのKVキャッシュを直接制御する研究。本文主要節・付録を部分読了／コード・再現未実施。

- [Raw-RAGとエージェント記憶の比較](2026-raw-rag-agentic-memory.ja.md)（[arXiv:2610.30755v1](https://arxiv.org/html/2610.30755v1)、2026）— 原履歴検索と複雑な記憶管理の比較。一次本文・付録の一部を確認／部分読了／コード・再現未検証。

- [Google Sleep：継続学習と記憶の定着](2026-google-sleep-continual-learning.ja.md) — Google記事と元論文を部分確認、再現未実施。

[サーベイ索引](../README.ja.md) | [リポジトリREADME](../../README.ja.md)

- [RecursiveMAS：潜在表現によるエージェント協調](2026-recursive-multi-agent-systems.ja.md) — 紹介記事と論文を1研究に整理、v2主要部分確認、再現未実施。
