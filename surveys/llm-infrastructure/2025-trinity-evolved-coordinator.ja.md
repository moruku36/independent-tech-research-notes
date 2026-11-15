**日本語** | [English](2025-trinity-evolved-coordinator.md)

# TRINITY：モデルと役割の選択を学ぶ

## 概要

- **何についてのものか** 異なるLLMをまとめる軽量なコーディネーターの研究。
- **何を述べているか** 隠れ状態を使うヘッドが、各ターンでモデルと3種類の役割を選ぶ。
- **留意点** 報告された効果は、ワーカープール、評価予算、ベンチマーク版に依存する。

## 実務向けの読み解き（6行）

- Qwen3-0.6Bのバックボーンから文脈表現を得る。
- 約1万パラメータのヘッドでモデルとThinker・Worker・Verifierを選ぶ。
- ヘッドと特異値の尺度を、小さな学習対象として調整する。
- sep-CMA-ESでタスク全体の成績から協調を最適化する。
- LiveCodeBenchのpass@1は指定の2025年1〜4月分で86.2%と報告する。
- 応用案は、計画・実行・検証の予算付き振分けを同条件の固定手順と比較すること。

## 書誌・確認範囲

Jinglue Xu、Qi Sun、Peter Schwendeman、Stefan Nielsen、Edoardo Cetin、Yujin Tang『TRINITY: An Evolved LLM Coordinator』。arXiv:2512.04695v3、2026-04-27、初版2025-12-04。2026-11-15 JSTに§2〜4を部分確認。ICLR 2026は書誌記載で、旧版差分は未確認。

## 証拠・限界

主要設定は7ワーカー、最大5ターンで、比較時には出力トークン予算を調整する。Verifierの受理はモデルの判断で、正しさの証明ではない。進化学習にもワーカー呼出しが必要で、学習パラメータが小さいことと総費用が小さいことを区別する。

## 関連資料

- [Conductor](2025-conductor-natural-language-orchestration.ja.md)
- [Fugu記事と一次報告の照合](2026-fugu-orchestration-report-review.ja.md)
- [エージェント構成とスケール](2025-scaling-agent-systems.ja.md)

## 無料の確認計画・活用状態

提案・未実施。まず無料で役割の契約、停止条件、外部の受入テストを振分け記録票にまとめる。後のローカル比較ではプール、課題、総予算を固定して、固定手順と適応型を比べる。成功、誤検証、呼出し数、遅延を記録する。次は学習済みモデル、学習成果物、評価分割を確認する。学習・モデル呼出しは未実施。

## 出典

- [依頼された資料](https://arxiv.org/abs/2512.04695v3)
- [確認した本文](https://arxiv.org/html/2512.04695v3)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
