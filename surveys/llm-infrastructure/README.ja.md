**日本語** | [English](README.md)

# LLM推論基盤と費用対効果

LLM推論のハードウェア選択、スケジューリング、KVキャッシュ制御、長期記憶検索。


## 2026-11-15追加

- [Unsloth Qwen3.8：量子化とローカル実行](2026-unsloth-qwen38-local-inference.ja.md) — 提供元ガイド。27Bの範囲とメモリ単位を確認。
- [DGX Station 2台でのGLM-5.3：容量と同時実行](2026-glm53-two-dgx-stations.ja.md) — 提供元手順記事。全体スループットと遅延を確認。

## 2026-11-13追加

- [エージェントの協調構成とタスクの適合](2025-scaling-agent-systems.ja.md) — プレプリントv3。協調構成の結果と評価範囲を確認。
- [DLiteによる履歴を持たない投機的デコーディング](2026-dlite-history-free-speculation.ja.md) — プレプリントv1。構成と推論指標を確認。

## 2026-11-12追加・再確認

- [EC2-Benchによる端末・クラウド協調エージェントの評価](2026-ec2-bench-edge-cloud-agents.ja.md) — プレプリントv2。課題の選定と露出指標を確認。
- [HARPの選好推定・撤回済みプレプリント](2026-harp-preference-inference-withdrawn.ja.md) — v2で撤回。旧v1を履歴資料として確認。
- [RIVETルーティング・v2再確認](2026-rivet-multiturn-llm-routing.ja.md) — 既存ノートを再確認。新規論文としての重複登録なし。

## 2026-11-11追加

- [ShatteredによるLLM自前運用とAPIの費用比較](2026-shattered-self-hosted-llm-vs-api.ja.md) — 編集記事。仮定を置いた費用試算。

## 2026-11-10追加

- [Cloud Pathways GA：複数スライスのML実行ランタイム](2026-google-cloud-pathways-ga.ja.md) — 一次資料を部分確認、再現未実施。
- [GKE dynamic slicing：TPUの資源形状と障害復旧](2026-google-gke-dynamic-slicing.ja.md) — 一次資料を部分確認、再現未実施。
- [TPU Sync：KVキャッシュとモデル重みの転送](2026-google-tpu-sync.ja.md) — 一次資料を部分確認、再現未実施。
- [Nexus：クラウド・エッジ・端末をまたぐ実行と権限](2026-nexus-cloud-edge-execution.ja.md) — 一次資料を部分確認、再現未実施。
- [Let Them Sleep：RSPMの記憶整理と削りすぎの問題](2026-rspm-self-pruning-memory.ja.md) — 一次資料を部分確認、再現未実施。
- [Do agents need to sleep?：記憶整理をめぐる検証可能な仮説](2026-do-agents-need-sleep.ja.md) — 一次資料を部分確認、再現未実施。

## 2026-11-09追加

- [OpenClaw Dreaming：根拠付きの外部記憶を整理・昇格する](2026-openclaw-dreaming-memory-consolidation.ja.md) — 公式製品文書。外部記憶の段階・由来・書き換え検証を確認／コード・実動作未検証。

## 2026-11-08追加

- [Anthropic：エージェント記憶を構成する四つの層](2026-anthropic-agent-memory-components.ja.md) — 企業技術記事。外部記憶・検索・wikiの事例を確認／回答時の節約と準備費用を区別／再現未実施。

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
