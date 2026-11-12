**日本語** | [English](2026-antigravity-hydrogen-orchestrator.md)

# Google AntigravityのHydrogenとOrchestrator

## 概要

- **何についてのものか** AntigravityでのHydrogenとOrchestrator選択肢の発表。
- **何を述べているか** 同一セッション内でCarbonの計画とHydrogenの実行を切り替える。
- **留意点** 改善値は提供元の評価。確認した発表ページ間でベンチマークの版が異なる。

## 実務向けの読み解き（6行）

- Carbonが状況を読み、再計画の条件を含む手順を作る。
- Hydrogenが編集と検査を進め、必要に応じて処理を戻す。
- 並列エージェントと別worktreeを使うSwarmとも関連する。
- 記事はHydrogenを有料Pro・Ultra、Orchestratorを当初Ultra向けと説明する。
- 応用案は、同じ課題で成功、時間、クォータを比べること。
- 提供対象と測定構成を、結果と一緒に版固定する。

## 書誌・確認範囲

Antigravityチーム、2026-11-12。2026-11-13 JST確認。Web直接取得は失敗したため、ブラウザの公式日本語表示で本文を読み、変更履歴とGoogle発表も照合。

## 内容・証拠・限界

双方向のモデル切り替えと、SDKで役割を明示する方法を紹介する。日本語本文は比較をTerminal-Bench 4.1、Googleの総合発表は4.0と記載している。両測定の対応関係は未解決として記録する。

## 関連資料

- [Gemini 4 Hydrogen発表](../articles/2026-google-gemini-4-hydrogen.ja.md)
- [RIVETルーティング](../llm-infrastructure/2026-rivet-multiturn-llm-routing.ja.md)
- [Swarmの利用者報告](2026-antigravity-swarm-reddit-report.ja.md)

## 無料の確認計画・活用状態

提案・未実施。管理下の同じ編集課題と固定の検査を使い、単一モデル、Orchestrator、上限を決めた並列実行を比較する。次は提供状況、ベンチマークの版、切り替え時の状態保持を確認する。

## 出典

- [Submitted Antigravity article](https://antigravity.google/blog/gemini-4-hydrogen-in-google-antigravity/)
- [Google model announcement](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/)
- [Official changelog](https://antigravity.google/docs/changelog/)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
