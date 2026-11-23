**日本語** | [English](2026-anthropic-claude-ship-review-approval.md)

# Claude Ship：プルリクエストのレビュー・修正・承認

## 概要

- **何についてのものか**：Claude Team・EnterpriseのGitHubプルリクエスト向け機能についてのAnthropicの製品発表。
- **何を述べているか**：Code Reviewが指摘を出し、PR Stewardが修正を担当し、Claude Approvalsがリポジトリの方針で承認を判断する。
- **留意点**：新しい2機能はベータ。利用条件、料金、承認の権限は組織とリポジトリの設定による。

## 実務向け6行

- Code Reviewは一般提供され、プルリクエストに指摘を投稿する。
- ベータのPR Stewardはチェック失敗やレビュー指摘への修正を担当し、承認とマージは担当外。
- ベータのClaude Approvalsは、リポジトリの方針が許す定型変更を承認できる。
- 観察モードは判断だけを示す。マージの可否はGitHub側の必須チェック、ブランチ保護、権限にも従う。
- 発表ではゼロデータ保持、HIPAA構成、顧客管理暗号鍵を利用対象外とし、観察モードでも方針によりレビューが課金される。
- 応用案は、承認を必須にする前に、過去の変更を使って観察モードの判断と人の判断を照合すること。

## 書誌・確認範囲

Anthropic、2026年11月23日。2026年11月24日（JST）に発表と製品ページを確認。リポジトリの設定変更、製品試用、効果の再現は未実施。

## 根拠と限界

- **役割と強制。** 指摘はCode Review、修正のプッシュはPR Steward、承認の判断はClaude Approvalsが担う。接続済みリポジトリの既定ブランチにある方針を使い、マージ条件には既存のブランチ保護と必須チェックが効く。
- **提供条件と証拠。** 発表の対象はTeam・EnterpriseのGitHubリポジトリ。Claude Codeチームでマージ件数が増え、取り消しの割合が減ったとの報告は、より広い開発手順の中での比較。Claude Ship単独の効果は切り出せない。観察モードも、方針がCode Reviewを使う場合は課金対象になり得る。

## 応用・無料の確認案

提案。架空のプルリクエストを人の承認が必要かどうかで判定し、レビュー記録を対象コミットにひも付け、人の判断と比較する。CIをやり直した場合や、承認方針自体の変更も題材にする。

## 関連ノート

- [Claude Codeの検証実践](2026-claude-code-verification-practices.ja.md)

## 出典

- [Claude Shipの発表](https://claude.com/resources/articles/introducing-claude-ship)
- [指定の日本語ページ](https://claude.com/ja/resources/articles/introducing-claude-ship)
- [Claude Shipの製品ページ](https://claude.com/product/claude-ship)

[分野別索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
