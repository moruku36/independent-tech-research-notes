**日本語** | [English](README.md)

# コーディングエージェント・コードレビュー・開発現場

AIコーディング支援・自動修復・自動レビューのベンチマークと企業での実証研究。


## 2026-11-15追加

- [重み固定の自己改善：失敗記録の追加効果](2026-frozen-weight-failure-trace-lessons.ja.md) — プレプリントv2。対応する対照条件と転移の限界を確認。

## 2026-11-14追加

- [Rust 1.100：言語・メモリ管理・Cargoの変更](2026-rust-1-100-release.ja.md) — 公式リリース記事。互換性とCargoの主要変更を確認。
- [CAMP-II：文脈をまたぐファイル記憶の学習](2026-camp-ii-file-memory-distillation.ja.md) — プレプリントv2。学習方法と改善倍率の分母を確認。
- [ParallACT：共有コードで独立した依頼を調整する](2026-parallact-shared-code-coordination.ja.md) — プレプリントv1。統合後の正しさと比較条件を確認。

## 2026-11-13追加

- [正しいソフトウェアを書く難しさと計算量](2016-correctness-and-complexity.ja.md) — 2016年の技術論考。主要な議論を確認。
- [Google AntigravityのHydrogenとOrchestrator](2026-antigravity-hydrogen-orchestrator.ja.md) — 公式製品記事。ブラウザ本文で確認。
- [Reddit利用者によるSwarm開発試行](2026-antigravity-swarm-reddit-report.ja.md) — コミュニティ報告。公式の手順説明と照合。

## 2026-11-12追加・再確認

- [GitHubのエージェント規模向けGit基盤](2026-github-git-infrastructure-agent-scale.ja.md) — 企業技術記事。基盤設計と内部測定の範囲を確認。
- [The Agentic Scientistによる研究の並列実行と証拠管理](2026-sakana-agentic-scientist.ja.md) — プレプリントv1。手順と限界を確認。

## 2026-11-11追加

- [CWE-benchによるリポジトリの防御的な修正評価](2026-cwe-bench-defensive-repair.ja.md) — ベンチマークのプレプリントv2。修正の判定条件と表3を確認。
- [AlphaProof Codeによるlibsignalの機械検証](2026-google-alphaproof-code.ja.md) — 発表記事と技術論文の該当箇所を確認。
- [Evan X. Merzが指摘するAI支援開発とコードの脆さ](2026-merz-ai-codebase-fragility.ja.md) — 開発者の実務論考。対照測定なし。

## 2026-11-10追加

- [AIによる量子プログラム発見と形式検証](2026-formally-verified-quantum-discovery.ja.md) — プレプリントv2。仕様固定・外部証明検査・資源指標を部分確認／再現未実施。
- [Organon：科学的探索の進め方そのものを改訂する](2026-organon-scientific-discovery.ja.md) — 一次資料を部分確認、再現未実施。

## 2026-11-09追加

- [SKILL-SIF：カーネル監査スキルの限界と失敗からの改善](2026-security-skills-kernel-skill-sif.ja.md) — プレプリントv1。ファイル誘導型の監査とスキル改訂を部分確認／絶対成功率と改善倍率を区別／再現未実施。
- [AIのIaC変更：PRの出自・採用率・持続可能性の観察研究](2026-agent-iac-pull-request-study.ja.md) — 観察研究プレプリントv1。出自判定・リポジトリ内比較を確認／集計表記の差を記録／再分析なし。

## 2026-11-08追加

- [AGENTS.md・CLAUDE.mdの実態：公開リポジトリの指示ファイル調査](2026-agents-claude-instruction-file-census.ja.md) — 観察研究プレプリントv2。ルート指示ファイルの普及・内容を確認／効果や実利用とは区別。

## 2026-11-07追加

- [MASS：複数エージェントの実行記録から学ぶ再帰的自己改善](2026-mass-multi-agent-self-supervision.ja.md) — プレプリントv1。ワークフロー探索と追加学習／出力トークン効率と総費用を区別／再現未実施。

- [The AI Scientist：研究工程から論文作成・自動査読まで](2024-sakana-ai-scientist.ja.md) — 研究記事＋対応論文v3。2024年版の工程・評価・限界を部分確認／自動査読と実際の採択を区別／再現未実施。
- [Darwin Gödel Machine：自分のコードを改善するエージェント](2025-sakana-darwin-godel-machine.ja.md) — 研究記事＋対応論文v3。固定モデルでのコード自己改善／段階評価と全体評価を区別／再現未実施。

- [量子化で変わるコーディングエージェントの解き方](2026-quantization-coding-agent-behavior.ja.md) — プレプリント。一次本文・主要表を確認／有意差なしと同等性を区別／再現未実施。

## 2026-10-28追加

- [Scion解説：Gitの前提とエージェント規模の開発基盤](2026-scion-qiita-design-review.ja.md) — 一次記事を解説する個人の技術記事。Qiita公式APIから本文・作成日時を確認。Scionの一次記事は既存ノートを参照。今回の数値・Entire等の追加資料は独立再検証していない。
- [ハーネス蒸留でエージェントの周辺設計はどう変わるか](2026-harness-distillation-commentary.ja.md) — 研究を論じる技術解説・論説。検索サービスが返した記事本文を確認。引用研究Harness-Zero・RRSIの一次論文と実験は未検証。
- [現代AI入門：モデルから思考するシステムへ](2026-thinking-systems.ja.md) — IBISチュートリアルの登壇資料。公開説明とトランスクリプトの主要節を部分確認。全図表・引用論文の個別検証は未実施。

- [MicrosoftのAIエージェントによるコード移行と仕様駆動開発](2026-microsoft-agentic-code-modernization.ja.md)（2026-10-26）— 企業技術記事。本文確認／移行・証明の独立検証と再現は未実施。

- [Claude Codeチームのコードレビュー](2026-claude-code-review.ja.md) — 企業技術記事。元記事本文確認、X投稿・PDF本文は未確認／再現未実施。

- [Anthropicのソース管理再設計：Scion](2026-anthropic-scion-source-control.ja.md) — 研究動向報告・技術記事の読書ノート。部分確認／再現未実施。

- [サブエージェントをメインループへ統合すべき条件](2026-fold-subagents-main-loop.ja.md)（2026-10-22）— 技術記事。本文確認済み／移行キット未実行。論文件数とは区別。
- [Neuro-Formal Verification](2026-neuro-formal-verification.ja.md)（v1、2026-08-21）— プレプリント。方法・評価・誤り分析確認／部分読了／再現未実施。

- [LLMによる形式的ソフトウェア検証](2026-anthropic-formal-verification.ja.md)（2026-10-22）— Anthropicの研究記事。一次資料確認済み／独立検証・再現未実施。学術論文件数とは別に収録。

- [SlopCodeBench — 反復開発におけるAI生成コードの品質劣化](2026-slopcodebench.ja.md)（v2、2026-05-07）— 自身のコードを36問題・196段階で拡張し、正しさ・構造劣化・冗長性を評価。一次PDF本文・主要表・実行条件確認済み／再現未実施。
- [SWE-Journey](2026-swe-journey.ja.md)（2026-10-08）— 長期開発と模擬利用者の対話を評価。一次本文確認済み／部分読了／実験未実施。
- [FlowAgent](2026-flowagent.ja.md)（2026-10-05）— Googleの提出前テスト失敗を低遅延で自動修復。一次PDF確認済み／再現未実施（非公開ツール）。
- [人中心からエージェント型コードレビューへ](2026-agentic-code-review-eras.ja.md)（v1、2026-07-14）— 207のGitHubプロジェクト・102万件のレビュー済みPRの変遷。一次PDF本文確認済み。
- [コマンドラインAIコーディングエージェントの導入と影響](2026-cli-coding-agents-adoption-impact.ja.md)（v1、2026-07-01）— Microsoftにおける端末向けコーディングエージェントの利用ログとアンケート調査（n=3,812）。一次PDF本文確認済み。
- [Metaにおける低リスク・コードレビューの自動化（RADAR）](2026-radar-low-risk-code-review.ja.md)（v2、2026-06-12）— 53.5万件超のDiffを処理したリスク階層型レビュー・自動マージ基盤（DRS＋LLM ACR）。一次PDF本文確認済み。

[サーベイ索引](../README.ja.md) | [リポジトリREADME](../../README.ja.md)

- [自律ML開発と簡素なハーネス](2026-ml-engineering-minimal-harness.ja.md) — 一次HTML主要部分確認、評価条件に限定、再現未実施。

- [Evolving Agent Teams：停滞に応じたチーム再編](2026-evolving-agent-teams.ja.md) — 一次HTML主要部分確認、原文の不一致を記録、再現未実施。

- [AutoHarness：行動検証コードの自動生成](2026-autoharness-code-synthesis.ja.md) — 一次HTML主要部分確認、有限のゲーム評価、再現未実施。


- [構造化出力の失敗](2026-structured-output-failure.ja.md) — 原文主要部分を確認、再現未実施。
