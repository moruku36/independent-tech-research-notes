**日本語** | [English](2026-nvidia-openshell-infrastructure.md)

# NVIDIA OpenShellとKubernetes上のエージェント基盤

## 概要

- **何についてのものか** KubeConで発表された、Kubernetes上のエージェント統制とGPU基盤のNVIDIA記事。
- **何を述べているか** 実行時にポリシーを適用するOpenShellがCNCF Sandboxに入り、Agent SubstrateやGPU基盤の取り組みも紹介された。
- **留意点** プロジェクト採択、統合作業、パートナーによる測定は、確認できることがそれぞれ異なる。

## 実務向けの読み解き（6行）

- OpenShellはツール利用や推論サービスへのアクセスなどに実行時ポリシーを適用する。
- Agent Substrateは、アイドル時の休止を含むKubernetes上のエージェント環境のライフサイクルを扱う。
- NVIDIAとGoogleは両プロジェクトの統合作業を進めている。
- Kubernetes EngineとRecipesは公開プレビューで、Snapshotは推論レプリカの起動と復旧を対象にする。
- 研究ハーネスへの応用案は、権限・作業環境の状態・実行の開始と休止を別々に記録すること。
- 本番への適合は、実際に使うバージョン、ポリシー、統合機能に左右される。

## 書誌・確認範囲

Warren Barkley、NVIDIA Blog、2026-11-10。2026-11-11 JSTにエージェント統制と基盤の節を読み、CNCF発表でSandboxへの参加を照合した。

## 手法・証拠・限界

発表はOpenShellの決定的なポリシー制御と、Agent Substrateの環境保存・アイドル時休止を説明する。両者を組み合わせる取り組みは統合作業として報じられている。Snapshotの数値は特定GPUとワークロードでパートナーが測った推論の起動・準備時間。OpenShellの制御や統合構成の性能は別の根拠で確認する。

## 関連研究・記事

- [Kubernetes上の自律エージェントの封じ込め](2026-kubernetes-autonomous-agent-containment.ja.md)

## 無料の確認計画・活用状態

提案・未実施。自分が管理する無害な研究タスクを想定し、ダミー入力で必要なファイル・ツール・推論先・休止時に保持する状態を表にする。資料上の両プロジェクトの責務と照合し、次にバージョン別のポリシー適用の根拠と統合状況を確認する。デプロイとベンチマークは未実施。

## 出典

- [NVIDIA article](https://blogs.nvidia.com/blog/open-source-openshell-infrastructure/)
- [CNCF OpenShell announcement](https://www.cncf.io/blog/2026/11/10/welcoming-openshell-to-the-cncf-open-governance-to-secure-agentic-ai/)
- [CNCF project announcements](https://www.cncf.io/announcements/2026/11/10/cncf-hits-major-milestones-with-global-community-growth-record-industry-investment-and-a-new-generation-of-projects-to-build-ai-systems-in-production/)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
