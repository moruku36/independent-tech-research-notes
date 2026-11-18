**日本語** | [English](2026-aws-well-architected-foundations-workloads.md)

# AWS Well-Architected 2026のクラウド基盤とワークロード

## 概要

- **何についてのものか** AWSのクラウド設計ガイダンスの更新。
- **何を述べているか** 共通統制はCloud Foundations、個別設計はCloud Workloadsに整理した。
- **留意点** 数値は指針の項目数。運用への効果は今回未検証。

## 実務向け6行

- アカウント共通の統制は、それを引き継ぐ各ワークロードの前提として評価する。
- 基盤編は7領域・45項目で構成される。
- ワークロード編は移管・統合・廃止により307項目から216項目になった。
- 6つの柱にはセキュアコーディングやバックアップ保護の指針が追加された。
- 共通統制と個別の確認項目に、担当者と確認の根拠を割り当てる。
- 設定やテレメトリーから判断できない事項は、人のレビューで扱う。

## 書誌・確認範囲

AWS Architecture Blog、2026年11月16日公開。11月19日 JSTに、指定された日本語パスに代えて、AWSが11月18日に公開した公式日本語訳とリリースノートを確認。

## 根拠と限界

公式リリースノートでは6つの柱のホワイトペーパー統合を確認。基盤編45項目のうち33項目は既存の柱からの移管・統合に由来する。技術範囲を維持したという説明はAWSの主張で、レビュー時間の削減を示す測定値は記事にない。

## 応用・無料の確認案

提案／未試行。既存ワークロード1件のチェック項目を、共通のID管理・ログ・コスト統制に対応づけ、バックアップからの復旧可否を示す証拠を個別に整理する。

活用状態は提案。今回の読書ノート作成では実環境での再現や導入を行っていない。

## 出典

- [AWS official Japanese translation](https://aws.amazon.com/jp/blogs/news/announcing-updates-to-the-aws-well-architected-framework-3/)
- [AWS release notes](https://docs.aws.amazon.com/wellarchitected/latest/framework/release-notes.html)

[テーマ索引](README.ja.md) · [読書一覧](../../docs/reading-list.ja.md)
