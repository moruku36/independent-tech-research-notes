**日本語** | [English](2026-mit-htmaa-agentic-engineering-resources.md)

# MIT HTMAA 2026：ものづくり教材とエージェント工学

## 概要

- **何についてのものか**: 単一論文ではなく、デジタル加工の講義資料集。
- **何を述べているか**: 選択した講義は、工学ツール・フィードバック・独立した検証を結び付ける。
- **留意点**: 研究の紹介と教育用デモを含み、全カリキュラムを監査したわけではない。

## 実務向けの読み解き（6行）

- 問いは、CAD・シミュレーションなどをエージェントがどう使うか。
- 講義はコード、構造化呼出し／MCP、GUIを比較する。
- 実行可能な検査と、提案・評価の分離を重視する。
- 応用案は、生成前に単位・制約・失敗条件を明示すること。
- 調整とソルバーの費用を測ってから、独立した評価を並列化する。
- 歯車デモはLLMトークン0のスクリプトで、AIエージェントの性能実験ではない。

## 書誌・確認範囲

MIT Center for Bits and Atoms、*How To Make (almost) Anything*、MAS.863/4.140/6.9020、2026年度講義サイト。選択資料：Ric Fulop、*Agentic Engineering*、10月1日補講（表紙にはSeptember 2026も併記）。

2026-11-17に日程・AI補講索引・Ricのスライドを確認し、ツール比較・スクリプト実演の図も目視。Sayam資料は部分確認。Eitan資料・他講義・コードは未精読。

- [指定URL](https://pub.cba.mit.edu/863.26/site/)
- [AI recitation](https://pub.cba.mit.edu/863.26/site/recitations/AI/index.html)
- [Ric's slides](https://pub.cba.mit.edu/863.26/site/recitations/AI/Ric.pdf)

## 方法・証拠と限界

Ric資料p.10・30〜33は、ツール接続、シミュレーションの並列化、検証、製作前承認を分ける。日程は設計から統合までを扱い、確認日の時点で11月18日以降は予定である。

## 関連資料との比較

引用される[協調構成の研究](../llm-infrastructure/2025-scaling-agent-systems.ja.md)の数字を、独立したMIT実験として二重に数えない。[WorkflowArena](../llm-infrastructure/2026-workflowarena-executable-orchestration.ja.md)の統合受入と、教材の検証項目を比較できる。

## 無料の確認案・活用状態

無料の確認案・未実施：寸法の不変条件を持つ単純な形状を定義し、意図的な不正例と正常例を独立スクリプトで確認する。生成と検証を分けて記録する。スキーマ・検査器の練習であり、製造安全の認証やソルバー実演の再現ではない。

活用状態：提案／未試行／未採用。論文・発表の結果を再現したとは扱わない。

## 未確認点・次の確認

次は対象課題・ツールのライセンス・検査器・引用元論文を確認する。工作機械や実機は操作していない。

[分類索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
