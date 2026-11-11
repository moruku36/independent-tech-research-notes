**日本語** | [English](2026-qwen4-max-preview.md)

# Qwen4-Max-Previewの提供条件と出力予算

## 概要

- **何についてのものか** Alibaba Cloudによるqwen4-max-previewの公式資料。
- **何を述べているか** マルチモーダル入力、推論、ツール呼び出しと、期間限定のToken Planでの提供条件を示す。
- **留意点** 提供元の仕様説明。能力や互換性の独立テストは未実施。

## 実務向けの読み解き（6行）

- テキスト、画像、動画を入力し、テキストを返すモデルとして説明される。
- 文脈長は1Mトークン、最大出力393,216トークンは推論と最終回答で共有する。
- Chat Completionsのmax_tokensも、その合計の出力予算を制限する。
- 専用の接続先を使うToken Planで提供する。
- 資料上のプレビュー終了は11月25日24時（UTC+8）で、その後は提供終了予定。
- 接続部への応用案は、固定の合成入力で打ち切り、構造化出力、ツール結果を試すこと。

## 書誌・確認範囲

Alibaba Cloud Model Studio。2026-11-11更新、2026-11-12 JST確認。能力、仕様、提供条件、利用上の注記を確認。API呼び出しは未実施。

## 方法・証拠・限界

Chat Completions、Responses、Anthropic Messagesとの互換性を記載する。パラメータやツールの実際の挙動は方式別に確認する必要がある。文脈容量は仕様値で、検索精度や遅延には別の測定が要る。

## 関連資料

- [Kimi K3.1 Proの公開報道](2026-emergent-kimi-k31-pro.ja.md)

## 無料の確認計画・活用状態

提案・未実施。JSONの妥当性、無害なツール応答、長文中の質問の例を用意し、期待結果と比較可能な予算を先に記録する。次はプレビュー後の提供状況と移行先の資料を確認する。

## 一次資料

- [Model documentation](https://www.alibabacloud.com/help/en/model-studio/qwen4-max-preview)
- [API compatibility changes](https://www.alibabacloud.com/help/en/model-studio/api-compatibility-upgrade-notice)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
