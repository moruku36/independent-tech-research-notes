**日本語** | [English](2026-emergent-kimi-k31-pro.md)

# EmergentによるKimi K3.1 Proの重み公開報道

## 概要

- **何についてのものか** MoonshotがKimi K3.1 Proの重みを配布したことを伝えるニュース記事。
- **何を述べているか** モデルカードは総2.8兆・活性1040億パラメータ、最大1,048,576トークンの文脈長を示す。
- **留意点** 評価スコアは開発元の測定で、実運用時の挙動は実行基盤やタスクに依存する。

## 実務向けの読み解き（6行）

- マルチモーダルな混合専門家モデルの重み配布を扱う。
- Moonshotは量子化を考慮した学習を行い、重みをMXFP4、活性をMXFP8と記載する。
- Terminal-Bench 4.0の65.7はMoonshotの評価結果として報じられた値。
- 文脈長は入力容量の仕様なので、離れた箇所から根拠を拾えるかは別に評価する。
- エージェント研究への応用案は、入力内で根拠が置かれる位置を変えた比較。
- 重みには独自ライセンスがあり、予定する用途に当てはまる条項を本文で確認する。

## 書誌・確認範囲

Kyle Morrison、Emergent、2026-11-05。2026-11-11 JSTに記事とMoonshotモデルカードの構成・評価項目を確認。記事は重みの配布日を11月4日とする。

## 手法・証拠・限界

記事のスコアは開発元の評価条件に基づく。モデル間比較ではツール利用、推論設定、採点方法が効く。活性パラメータはトークンごとの計算に関わる値で、運用の見積もりでは重み全体と文脈の状態、実行基盤の追加負荷も考える。API提供と重み配布は日付と利用条件が異なり得る。

## 関連研究・記事

- [自前運用とAPIの費用比較](../llm-infrastructure/2026-shattered-self-hosted-llm-vs-api.ja.md)

## 無料の確認計画・活用状態

提案・未実施。正解に必要な根拠の位置を変えた短い合成文書を用意し、期待する回答と採点基準を先に書く。文脈予算を固定して検索、正答、遅延を測る計画にする。タスクの設計は重みの取得やモデル呼び出しなしで進められる。次は評価設定と実行要件を確認する。

## 出典

- [Emergent article](https://emergent.sh/news/moonshot-releases-kimi-k3-1-pro-2-8t-moe-1m)
- [Moonshot model card](https://huggingface.co/moonshotai/Kimi-K3.1-Pro)
- [Checkpoint license](https://huggingface.co/moonshotai/Kimi-K3.1-Pro/blob/main/LICENSE)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
