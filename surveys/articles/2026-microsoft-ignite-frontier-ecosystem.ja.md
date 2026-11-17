**日本語** | [English](2026-microsoft-ignite-frontier-ecosystem.md)

# Ignite 2026：企業エージェントを支える文脈・統制・モデル

## 概要

- **何についてのものか**: MicrosoftのIgnite基調講演を編集した、企業AI基盤の発表記事。
- **何を述べているか**: 仕事の文脈、モデル選択、エージェント管理、セキュリティを一体の構成として示す。
- **留意点**: 提供元の構想・発表であり、性能や導入効果の独立検証ではない。

## 実務向け6行

- 問いは、エージェントの能力を企業の管理可能な業務成果へどうつなぐか。
- Copilot、Microsoft IQ、Foundryのモデル、Agent 365、Perceptionをつなぐ構成を示す。
- 共有する文脈、組織の統制、独立に確認できる行動を重視している。
- 応用案は、一業務のデータ・モデル・権限・責任者・成果指標を対応付けること。
- 採用計画では、機能ごとの提供段階を別表にして確認する。
- 製品全体のGAを、すべての連携やプレビュー機能の提供済みと読み替えない。

## 書誌・確認範囲

Microsoft Corporate Blogs、2026年11月17日公開。Satya Nadellaの基調講演の編集版。2026年11月18日 JSTに指定本文をブラウザーで確認し、下記のAgent 365・Intuneの発表で提供段階を補足。一次資料を部分確認。導入・性能再現は未実施。

## 根拠と限界

基調講演では、Microsoft IQが企業の文脈、Agent 365が統制・可観測性、Perceptionがエージェント型セキュリティを担う。MAIの重みへのアクセスは対象顧客向けのライセンス提供であり、無制限なオープンウェイト公開とは異なる。効率に関する主張は提供元の報告。

個別のAgent 365記事ではBusiness AnalyticsはFrontier preview、一部連携はpreview・段階展開。IntuneのPerception機能は参加条件付きpublic previewとされる。上位の発表を要約しても、こうした限定条件は残す。

## 応用・無料の確認案

提案／未試行。架空の文書承認業務で、文脈の出所、許可行動、ID、レビュー証拠、費用、切り戻し、受入条件をローカル台帳にする。テナントを接続せず、今のGitHub・Codex運用と照合する。製品試行の前には地域・ライセンス・データ境界・提供段階・運用責任を確認する。

活用状態：提案／未試行／未採用。この記事の追加では、モデル呼び出し・環境変更・実験を実施していない。

## 関連ノート

- [Perceptionの詳細](../security-governance/2026-microsoft-perception-ignite.ja.md)
- [構成と費用の比較研究](../llm-infrastructure/2026-enterprise-sop-agent-architecture-cost.ja.md)

併読先としての比較であり、同条件の性能比較ではない。

## 出典

- [Supplied keynote / 指定の基調講演](https://blogs.microsoft.com/blog/2026/11/17/ignite-2026-building-the-frontier-ecosystem/)
- [Agent 365 feature status / 機能別の提供段階](https://techcommunity.microsoft.com/blog/agent-365-blog/whats-new-in-microsoft-agent-365-ignite-2026/4571753)
- [Perception in Intune / Intuneの提供条件](https://techcommunity.microsoft.com/blog/intunecustomersuccess/microsoft-perception-helps-it-drive-outcomes-and-scale/4573285)

[テーマ索引](README.ja.md) · [全読書一覧](../../docs/reading-list.ja.md)
