**日本語** | [English](2026-aws-emulator-local-testing.md)

# AWS Emulatorによるアプリケーションのローカル試験

## 概要

- **何についてのものか** AWS APIをローカルで模擬するAWS公式の発表記事。
- **何を述べているか** SDK・CLIをローカル接続先へ向けて試験でき、Rustのテスト内で動かす方式も紹介する。
- **留意点** APIの実装と振る舞いには不足がある。IAMやアカウント・リージョンをまたぐ挙動はAWS側での確認が要る。

## 実務向けの読み解き（6行）

- 開発者とコーディングエージェントの編集・試験ループに使う。
- ローカル接続先向けに認証情報と設定を生成する。
- Rustの組み込み方式では、テストごとに状態を分けられる。
- 未実装の操作には明示的なエラーを返す。
- ハーネスへの応用案は、ローカルの要件検査と後のAWS統合試験を組み合わせること。
- 資料のWindows・macOS向け導入方法はDockerを使う。

## 書誌・確認範囲

Daniel Abib、AWS News Blog、2026-11-11。2026-11-13 JST確認。日本語URLはWeb取得できなかったため英語原文と公式概要を参照。手順と制約を部分確認。

## 内容・証拠・限界

エミュレーター自体の追加サービス料金はないと説明し、後でAWS上に作る資源は課金対象となる。発表はIAM評価とアカウント・リージョン間の振る舞いを制約として挙げる。エージェントとレビューを使って実装範囲を広げる工程も紹介する。

## 関連資料

- [AI生成Terraformのガードレール](2026-ai-generated-terraform-guardrails.ja.md)

## 無料の確認計画・活用状態

提案・未実施。ダミーデータの小さな保存操作と期待結果を定め、ローカルでの挙動を先に確認する。次は操作の対応範囲と認可・展開時の差を調べる。インストールとクラウド資源の作成は未実施。

## 出典

- [Submitted Japanese URL](https://aws.amazon.com/jp/blogs/aws/test-your-applications-against-aws-locally-with-aws-emulator/)
- [English original](https://aws.amazon.com/blogs/aws/test-your-applications-against-aws-locally-with-aws-emulator/)
- [Official overview](https://docs.aws.amazon.com/emulator/latest/userguide/what-is-service.html)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
