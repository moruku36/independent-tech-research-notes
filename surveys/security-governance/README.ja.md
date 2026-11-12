**日本語** | [English](README.md)

# セキュリティ・ガバナンス（プライバシー・組織ポリシー・暗号アジリティ・クラウド統制）

GenAI利用・暗号移行・マルチクラウド統制の一貫性をめぐる、組織面のセキュリティの問い。

## 2026-11-12追加・再確認

- [CloudflareのGLM-5.3 KVキャッシュ露出と修正](2026-cloudflare-kv-cache-exposure.ja.md) — 提供者の障害・修正報告。影響範囲と対策の段階を部分確認。
- [Goldman SachsのコーディングAI利用制限に関する報道](2026-goldman-ai-coding-access-controls.ja.md) — Bloomberg報道。適用範囲・例外を確認、内部指針は未確認。
- [Anthropic利用ポリシー・2026年11月12日施行版](2026-anthropic-usage-policy-nov12.ja.md) — 提供者の利用規程。PDFと現行ページを照合。

## 2026-11-11追加

- [NVIDIA OpenShellとKubernetes上のエージェント基盤](2026-nvidia-openshell-infrastructure.ja.md) — NVIDIAとCNCFの発表を照合。

## 2026-11-09追加

- [Apiiro：エージェントの承認設定からGitHubへ漏れる秘密情報](2026-apiiro-agent-approval-secret-leaks.ja.md) — 企業調査記事。承認規則からの漏えい経路・件数の意味を確認／実際の秘密の探索・接続試験なし。

## 2026-11-08追加

- [Ubuntuの標準セキュリティ：Desktop・Serverとエージェントの隔離条件](2026-npaka-ubuntu-security-layers.ja.md) — 個人解説記事。本文・主要な公式資料を確認／AppArmor・Snap・UFWとDockerの条件を区別／実機検証未実施。
- [Macの標準セキュリティ：保護の層とAIエージェント利用時の限界](2026-npaka-macos-security-layers.ja.md) — 個人解説記事。本文・主要なApple公式資料を確認／OS間の優劣や防御率とは区別／実機検証未実施。
- [Windowsの標準セキュリティ：機能の適用条件とエージェントの権限](2026-npaka-windows-security-layers.ja.md) — 個人解説記事。本文・主要なMicrosoft公式資料を確認／機能の有効状態とアプリ権限を区別／実機検証未実施。
- [CVM-Store：機密VMの永続ストレージを守る設計](2026-cvm-store-confidential-vm-storage.ja.md) — システム論文プレプリントv1。脅威モデル・同期条件・性能を部分確認／再現未実施。

## 2026-11-06追加

- [Kubernetes上の自律エージェントを封じ込める多層防御](2026-kubernetes-autonomous-agent-containment.ja.md) — 一次資料の主要部分を確認。再現・独立検証は未実施。
- [OpenAIのLinuxカーネル脆弱性調査パイプライン](2026-openai-linux-kernel-vulnerability-pipeline.ja.md) — 一次資料の主要部分を確認。再現・独立検証は未実施。


- [QERS：IoT通信の耐量子暗号評価](2026-qers-pqc-iot.ja.md) — 一次本文を部分確認、結果に不一致あり。
- [NRIセキュア：指定ブログ確認待ち](2026-nri-ai-development-pending.ja.md) — 指定記事は未取得、関連公式発表は別資料として確認。

## 2026-10-30追加：AIエージェントのセキュリティ

- [危険な3条件（Lethal Trifecta）](2025-lethal-trifecta.ja.md)
- [OWASP エージェント型アプリケーションの10大リスク](2025-owasp-agentic-top10.ja.md)
- [Meta：エージェントの Rule of Two](2025-meta-rule-of-two.ja.md)
- [Google：AIセキュリティの防御戦略](2025-google-ai-security-frontier.ja.md)
- [CSA：MAESTRO 脅威モデリング](2025-csa-maestro.ja.md)
- [NVIDIA：Open Agent Safety Platform](2026-nvidia-open-agent-safety.ja.md)

## 2026-10-28追加

- [メルカリの全社エージェント活用とAIセキュリティ統制](2026-mercari-ai-security-governance.ja.md) — 登壇資料（AI×Security Conference 2026）。Speaker Deckの公開トランスクリプトを部分確認。多数のページは見出しのみ抽出され、図・詳細設定・発表音声は未確認。
- [Check PointとDaybreak：脆弱性調査から防御へ](2026-check-point-daybreak.ja.md) — 提供元の顧客導入事例。公式記事本文確認。時間短縮の測定条件、データ、実装は非公開で独立検証・再現未実施。

- [Claude Duetの安全設計](2026-claude-duet-safety-privacy-security.ja.md) — 公式製品記事。本文確認／独立検証未実施。
- [Claude Codeの記事公開時の漏えい経路](2026-claude-code-publication-leak-paths.ja.md) — 個人の実践記事。本文確認／再現未実施。

- [生成AIの禁止の次に必要なこと：シャドーAI・個人情報](2026-shadow-ai-ban-pii-governance.ja.md) — AIDB記事レビュー。主な参照論文と企業公式発表を確認。論文4本とは別計上。部分読了／再現未実施。

- [Agentic Inequality：AIエージェントを使える力の格差](2025-agentic-inequality.ja.md) — 一次資料を部分確認／実務向け7行・比較・限界・未実施の確認案を収録。

- [AWS・Azure・GCPを横断するマルチクラウド・セキュリティ設計](2026-multi-cloud-security-architecture.ja.md)（2026-09-24）— 出版元PDF本文確認。定量検証の記述不足／再現未実施。

- [Chat First, Worry Later](2026-chat-first-worry-later.ja.md)（v1、2026-08-21）— 職場でのChatGPT利用とシャドーAIに関する欧州企業従業員224名のアンケート調査。一次PDF本文確認済み。
- [CAMMの実用評価](2026-camm-practical-evaluation.ja.md)（v1、2026-04-14）— 暗号アジリティ成熟度モデル。一次PDF本文確認済み／再現未実施。評価条件・限界を整理。

[サーベイ索引](../README.ja.md) | [リポジトリREADME](../../README.ja.md)

- [エージェントの監査証拠を残すブラックボックス](2026-agentic-evidence-black-box.ja.md) — 設計提案、一次資料の主要部分確認、実証なし。

- [OSSへのAI貢献とガバナンス](2026-oss-machine-contributor-governance.ja.md) — 6組織の方針比較、一次HTML主要部分確認、独立した符号化未実施。

- [Google／Mandiant：LLMJackingによるクラウド資源の盗用](2026-google-llmjacking-cloud-resources.ja.md) — 企業の事例報告、公式検索結果の本文主要部分確認、独立検証未実施。

- [AIエージェントの透明性・説明責任・信頼性](2026-three-pillar-agent-oversight.ja.md) — 概念枠組み、一次資料主要部分確認。
- [量子安全な暗号の構成要素と移行事例](2026-quantum-safe-mechanisms-survey.ja.md) — 一次資料主要部分確認、引用研究の独立検証未実施。
