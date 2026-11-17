**日本語** | [English](2026-microsoft-perception-ignite.md)

# Microsoft Perception：エージェント型セキュリティと検証の範囲

## 概要

- **何についてのものか**: MicrosoftがIgniteで発表した、セキュリティエージェントの協調システム。
- **何を述べているか**: 人の統制の下で、red・blue・greenの役割が検査・調査・修復をつなぐ。
- **留意点**: 対象範囲、課題解決率、安全境界の遵守率は別の指標である。

## 実務向け6行

- 問いは、セキュリティの分析と修復をどう協調させるか。
- PerceptionはPlaybookと専門エージェントで処理し、結果の証拠を確認できる形にする。
- 記事の80%はアラートの対象範囲であり、正答率ではない。
- 応用案は、証拠収集・判定・承認・範囲を限定した修復を分けること。
- 実環境の検査前に、合成インシデントと読み取り専用の資料で確認する。
- GA、個別のプレビュー、パートナー評価の主張は別々に確かめる。

## 書誌・確認範囲

Hari PulapakaによるMicrosoft Community Hubの記事、2026年11月17日公開。2026年11月18日 JSTにブラウザー本文と脚注、関連するIntune発表を確認。提供元記事を部分確認。リンク先のIncalmo報告は取得できず、独立には確認していない。

## 根拠と限界

記事はPerceptionのGA、他社シグナル、API・MCPによる業務連携を説明する。トリアージ対象範囲はMicrosoftが約800万件のアラートを分析した集計で、個別顧客への保証ではない。

Web検査では、パートナー評価として解決率31.0%対Codex 15.2%、安全制約付き試験で境界遵守91%を引用する。異なる試験指標であり、安全の保証や今の利用環境のCodexへの優位を示すものではない。元の評価手順は未確認。関連するIntune機能はpublic previewで、全面GAではない。

## 応用・無料の確認案

提案／未試行。架空のインシデント資料を作り、各判断に根拠・対象範囲・不確実性・責任者・戻せる対応案を付ける。承認と復旧を机上確認し、スキャンや変更は実行しない。後の限定試行では誤検知、見逃し、範囲逸脱、確認時間、復旧結果を別々に測る。

活用状態：提案／未試行／未採用。この記事の追加では、モデル呼び出し・環境変更・実験を実施していない。

## 関連ノート

- [Ignite全体像](../articles/2026-microsoft-ignite-frontier-ecosystem.ja.md)
- [要件の引継ぎと完全性](../agent-safety/2026-signed-requirement-manifest-handoffs.ja.md)

併読先としての比較であり、同条件の性能比較ではない。

## 出典

- [Supplied article / 指定記事](https://techcommunity.microsoft.com/blog/perception-blog/whats-new-with-microsoft-perception-at-ignite-2026/4571834)
- [Intune public preview / Intuneのpublic preview](https://techcommunity.microsoft.com/blog/intunecustomersuccess/microsoft-perception-helps-it-drive-outcomes-and-scale/4573285)
- [Linked benchmark, uninspected / リンク先評価・未確認](https://aka.ms/incalmo)

[テーマ索引](README.ja.md) · [全読書一覧](../../docs/reading-list.ja.md)
