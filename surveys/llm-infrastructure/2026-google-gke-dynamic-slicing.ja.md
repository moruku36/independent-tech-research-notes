**日本語** | [English](2026-google-gke-dynamic-slicing.md)

# GKE dynamic slicing：TPUの資源形状と障害復旧

## 概要

- **何についてのものか**：TPUの実機確保と論理スライス割当を分けるGKE機能。
- **何を述べているか**：super-slicingで結合し、sub-slicingで分割する。
- **留意点**：機材・GKE・予約条件があり、適用範囲は限定される。

## 実務向けの読み解き（6行）

- 固定nodepool形状は配置の自由度を制約する。
- 事前確保した資源から動的に割り当てる。
- 記事は開始・復旧の短縮を報告する。
- 本ノートの提案：待ち時間と有効な完了を別測定する。
- 無料の確認は割当・障害時の遷移整理から。
- 一般GPUや自宅サーバーへそのまま使う機能ではない。

## 書誌・確認範囲

Kavitha Gowda、Wenzhe Li、Google Cloud、2026-11-09。製品技術記事。

確認日：2026-11-10 JST。直接openは失敗。検索経由の一次記事本文と公式概念資料を確認。クラスタ実行なし。
状態：一次資料確認済み／部分読了／再現未実施。

## 問い・方法・主張と証拠の読み方

開始最大5倍・復旧4.5倍は記事の条件付き主張。概念資料はIronwood／TPU7x、Standard／Rapid、方式別GKE版、All Capacity条件を指定。記事の広い地域表現だけで導入可とせず、仕様を優先する。

## 関連資料との比較

Pathwaysは実行制御、slicingは下層の資源形状として整理する。 [関連ノート](2026-google-cloud-pathways-ga.ja.md)

## 無料の確認計画・活用状態・次の確認

形状作成、障害分離、アプリ保存状態からの復旧を別工程として比較する案。無料の確認は公式条件表の作成。予約・クラスタ・有料実行なし。提案・未試行。次は対象地域、容量方式、実ワークロード基準を確認する。

## 一次資料

- [指定資料](https://cloud.google.com/blog/products/containers-kubernetes/gke-dynamic-slicing-on-tpus?hl=en)
- [同一記事の正規URL](https://cloud.google.com/blog/products/containers-kubernetes/gke-dynamic-slicing-on-tpus)
- [公式の補足仕様](https://docs.cloud.google.com/kubernetes-engine/docs/concepts/dynamic-slicing)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
