**日本語** | [English](2026-aws-api-ai-security-discovery-protection.md)

# AWSのAPI・AIセキュリティ：棚卸し、マネージドルール、保護範囲

## 概要

- AWSがAPI Portalの検出機能と、AWS WAFのAPI Security・AI Securityマネージドルールグループの一般提供を発表した。
- API Portalがエンドポイントを棚卸しし、2つのルールグループは関連付けたAWSリソースの通信を検査する。
- アプリ側の認可、対応リソース・リージョン、検査上限、検査呼び出し失敗時の扱いが設計に残る。

## 実務向け6行

- API Portalは対応するCloudFront、Application Load Balancer、API GatewayのREST APIを、通信と設定から棚卸しする。
- 単一アカウントやAWS Organizationsの組織単位で検出を有効化でき、通常のAPIとLLM推論・MCP・A2Aの入口を同じ一覧で追える。
- API Securityはリクエスト単位の検査と、通信パターンに基づく振る舞い検知を行う。振る舞い検知では確信度によって既定の処理が変わる。
- トークンの署名検証や、リクエスト先のオブジェクトに対する認可は引き続きアプリが担う。
- AI Securityはエージェント向けプロトコルを判別し、Amazon Bedrock Guardrailsによる内容検査も行う。レスポンス検査は有効化が必要で、本文の検査サイズに上限がある。
- Guardrailsの呼び出しが失敗すると、既定では通過させてラベルを付ける。可用性と監視の設計に関わる。

## 書誌・確認範囲

AWS Security Blog、2026年11月23日公開。11月25日（JST）に公式英語版と開発者ガイドを確認した。公開資料に基づく読書メモ。

## 根拠と限界

- API Portalは入口のサービスログと設定情報を使う。棚卸し上のエンドポイントとWAFの保護状況を照合できるが、対象範囲は対応リソースとWeb ACLの関連付けに依存する。
- API Securityの振る舞い検知は、リクエスト構造や通信パターンのほか、アプリが返すステータスコードも手掛かりにする。トークンの署名と個々のオブジェクトのアクセス権はアプリで判定する。
- AI Securityのプロトコル検査には対応するMCP・A2Aの版がある。Bedrock Guardrailsの内容検査はエンドポイント種別、リクエスト・レスポンスの方向、リージョンに依存する。発表は設定と例を示しており、独立した検知率や誤検知率の比較は掲載していない。

## 応用・無料の確認案

管理下のステージング環境で、棚卸しされた入口とWeb ACLの関連付けを照合する。ブロック対象を広げる前に、ラベル、レスポンス検査の適用範囲、正常リクエストの件数とエラー率を確認する。

## 関連ノート

- [MCPのサーバー・ゲートウェイ・プロトコル別の対策](2026-mcp-security-three-tier-mitigation.ja.md)
- [企業向けのコーディングエージェント保護](2026-anthropic-enterprise-coding-agent-security.ja.md)

## 出典

- [AWS Security Blog公式英語版](https://aws.amazon.com/blogs/security/introducing-api-and-ai-security-on-aws-from-discovery-to-protection/)
- [API Portal開発者ガイド](https://docs.aws.amazon.com/apigateway/latest/developerguide/apiportal.html)
- [AWS WAF API Securityのマネージドルール](https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-api-security.html)
- [AWS WAF AI Securityのマネージドルール](https://docs.aws.amazon.com/waf/latest/developerguide/aws-managed-rule-groups-ai-security.html)

[分野別索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
