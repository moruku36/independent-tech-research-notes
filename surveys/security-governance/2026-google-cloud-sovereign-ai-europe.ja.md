**日本語** | [English](2026-google-cloud-sovereign-ai-europe.md)

# 欧州向けGoogle Cloud Sovereign AI：運用主体と統制の範囲

## 概要

- **何についてのものか** 欧州でのソブリンAIの選択肢を示すGoogle Cloudの発表。
- **何を述べているか** パブリッククラウドの統制、パートナー運用の基盤、顧客施設での展開を説明する。
- **留意点** 提供段階や認定範囲はサービス、展開方式、国によって異なる。

## 実務向け6行

- Data Boundaryはパブリッククラウドの統制、Dedicatedは現地パートナー運用、Distributed Cloudは顧客施設での展開を担う。
- DedicatedへのGemini提供は予定として発表された。
- フランスのPREMI3NSでは、公開モデルや持ち込みモデル向けのマネージド推論が一般提供と発表された。
- Confidential External Key Managementはプレビュー。ルート鍵は顧客またはパートナーが管理する。
- スイス向けData Boundaryは提供済みで、EUのDORA向けは計画段階だった。
- 利用する機能を単位に、提供段階、鍵の管理者、認定範囲を確認する。

## 書誌・確認範囲

Jai Haridas、Google Cloud Blog、2026年11月17日公開。11月21日 JSTに公式記事の正規URLと、リンク先のS3NS発表を確認。提供段階は発表時点。

## 根拠と限界

S3NSによると、基盤はSecNumCloud 3.2認定済みで、新しいマネージドAIサービス層への認定拡張は手続き中だった。GoogleはcEKMについて、ルート鍵の管理をGoogle Cloud外に置き、鍵処理をハードウェアで真正性を確認した環境で行うと説明する。運用性能や個別ワークロードの適合性は独立検証していない。

## 応用・無料の確認案

提案／未試行。架空のワークロード1件について、運用主体、処理・保管場所、鍵の管理者、監査証跡、提供段階、認定範囲を表にする。

## 関連ノート

- [AWS Well-Architectedの基盤とワークロード](../cloud-resilience/2026-aws-well-architected-foundations-workloads.ja.md)

## 出典

- [Google Cloud announcement](https://cloud.google.com/blog/products/identity-security/sovereign-ai-on-your-terms-made-with-europe)
- [S3NS managed inference announcement](https://www.s3ns.io/en/news/ai-PREMI3NS-model)

[テーマ索引](README.ja.md) · [読書一覧](../../docs/reading-list.ja.md)
