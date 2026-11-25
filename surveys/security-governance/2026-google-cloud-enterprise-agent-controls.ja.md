**日本語** | [English](2026-google-cloud-enterprise-agent-controls.md)

# Google WorkspaceとCloudの企業向けエージェント統制

## 概要

- エージェントによるWorkspaceデータとCloudツールへのアクセス制御を扱うGoogleの公式発表。
- WorkspaceのMCPサーバーとCLIが一般提供になった。CloudのAgent Gatewayはリクエスト経路でID、ポリシー、設定した検査を扱う。
- 提供と適用の範囲は製品、配備方式、日程によって異なる。記事に独立した防御効果の測定はない。

## 実務向け6行

- Workspaceは管理型MCPサーバーとCLIを提供し、エージェント専用OAuthクライアント、スコープの制限、アクセス検査を組み合わせる。
- メール送信やDriveの共有変更など影響の大きい操作は利用者の確認を挟む。管理者はエージェントの活動を監査し、アクセスを取り消せる。
- 追加規約と技術的な適用は2027年2月1日予定。開発者資料では直接のREST呼び出しに対する制限と、4月1日のScaled Tier課金開始が説明されている。
- 規約は処理を承認済みの作業に限定し、学習への利用や派生情報の保持・利用を制限する。連携を解除した際にはデータ削除の義務もある。
- CloudのAgent GatewayはIAMと外向き通信の制御を担う。Model Armorなどの検査・拡張の適用は構成と配備方式に依存する。
- 応用案。架空データで許可スコープ、操作承認、監査ログ、アクセス取り消し、データ削除を確認する。

## 書誌・確認範囲

Chandu Thota、Brad Calder、Google Cloud Blog、2026年11月24日公開。11月26日（JST）に発表、Workspaceの追加規約と適用日程、Agent Gatewayの公式資料を確認。

## 根拠と限界

- Workspaceでは、期間限定の承認、利用者本人による活動確認、機密データのAIアクセス制限などに今後提供の項目がある。OAuthスコープ、情報漏えい防止（DLP）、分類ラベルはそれぞれ異なる制御を担う。
- 2月1日は追加規約とMCP要件適用の予定日。開発者資料はエージェントからの直接REST呼び出しにStandard Tierの上限が適用されると説明し、追加規約は対象の利用にGoogle MCPを求める。課金・クォータ適用は4月1日。Cloud Runと他クラウドのKubernetes向けGatewayには限定プレビューがある。
- Gatewayによる制御は経由する通信が対象。外向きポリシーやペイロード検査は方式と有効化された機能に依存する。機密操作には明示的な権限判断と独立した監査記録が重要になる。

## 応用・無料の確認案

提案・未試行。架空の文書を読む処理と影響の大きい操作を1件ずつ選び、ID、スコープ、送信先、承認、監査記録、削除の担当を対応づける。許可・拒否のケースとアクセスを取り消したときの前提を整理する。

## 関連ノート

- [MCPの層別セキュリティ対策](2026-mcp-security-three-tier-mitigation.ja.md)
- [企業のコーディングエージェント保護](2026-anthropic-enterprise-coding-agent-security.ja.md)

## 出典

- [Google Cloud公式発表](https://cloud.google.com/blog/products/identity-security/deploying-agents-safely-in-your-enterprise)
- [Workspace公式発表](https://workspace.google.com/blog/product-announcements/built-for-trust-and-control-new-ai-agent-protections-and-developer-tools-in-google-workspace)
- [Workspace AI Tools Addendum](https://workspace.google.com/terms/ai-tools/)
- [Workspaceのクォータと適用日程](https://developers.google.com/workspace/guides/quota-usage-tiers?hl=en)
- [Agent Gatewayの公式資料](https://docs.cloud.google.com/gemini-enterprise-agent-platform/govern/gateways/agent-gateway-overview)

[分野別索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
