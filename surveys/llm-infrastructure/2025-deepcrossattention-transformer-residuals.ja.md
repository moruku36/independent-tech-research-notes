**日本語** | [English](2025-deepcrossattention-transformer-residuals.md)

# DeepCrossAttention：Transformerの過去層から特徴を選ぶ残差接続

## 概要

- **何についてのものか**：Transformerが層をまたいで情報を運ぶ残差接続を見直す、Google Researchの解説とICML 2025論文。
- **何を述べているか**：DeepCrossAttention（DCA）は、過去層の出力をトークンごとに混ぜ、注意機構のクエリ・キー・値にも別々の組み合わせを使う。
- **留意点**：目標パープレキシティまでの時間、学習ステップ数、毎秒の処理量は別の指標で、モデルや保持する層の数によって変わる。

## 実務向け6行

- 標準の残差接続では層の出力を足し合わせる。DCAはトークンに応じて、どの過去層の出力を使うかを学ぶ。
- LM1Bの24層モデルでは、2-DCAが標準Transformerの最終パープレキシティに0.33倍の学習時間で達した。
- 同じ比較で毎秒の処理量は2-DCAが5.39バッチ、標準が8.14バッチ。目標までに必要なステップが減った。
- 解説記事では、言語モデルの評価で標準モデルの水準に達する学習ステップ数が最大で約5分の1だったと説明する。
- LM1Bの6層モデルにDCAを後付けし、6万ステップ追加するとパープレキシティが0.19低下した。標準構成での追加学習では0.02低下した。
- 応用案は、同じ損失に達する時間・ステップ数と、処理量・ピークメモリ・推論遅延を併記すること。

## 書誌・確認範囲

Kyriakos Axiotis、Thomas Fu、Google Research、2026年11月23日。対応するICML 2025論文の著者はMike Heddes、Adel Javanmard、Kyriakos Axiotis、Gang Fu、Mohammadhossein Bateni、Vahab Mirrokni。2026年11月25日（JST）に解説とarXiv:2502.06785v2の表1・4を中心に確認。学習・推論の再現は未実施。

## 根拠と限界

- **仕組み。** 混ぜ方は層とトークンで変わり、クエリ・キー・値がそれぞれ異なる過去層の出力を組み合わせられる。系列上のトークン間の注意に、深さ方向の情報再利用を加える。
- **学習の結果。** 表1では、LM1Bの24層Transformerの最終パープレキシティは15.14。2-DCAはその値に約3分の1の時間で達し、最終値は14.41。表4の6層モデルは18.98から出発し、6万ステップ追加後は標準構成が18.96、DCAを後付けした構成が18.79だった。
- **コスト。** 追加パラメータが少なくても、過去層の出力を保持し、読み出すとメモリへのアクセスが増える。論文は保持する出力数を変えた構成ごとの結果を示す。学習時間の改善から、標準Transformerより推論が速くなるとは判断できない。

## 応用・無料の確認案

提案。公開データで同程度の小型モデルを比較する。トークン化、文脈長、目標損失を固定し、毎秒のバッチ数、目標に達する時間と更新回数、学習時のピークメモリ、推論遅延を記録する。

## 関連ノート

- [Transformerの原著](2017-attention-is-all-you-need.ja.md)
- [Inkling 2 Miniの中間層反復](2026-thinking-machines-inkling-2-mini.ja.md)

## 出典

- [Google Researchの解説](https://research.google/blog/supercharging-transformer-residual-connections/)
- [ICML 2025論文情報](https://proceedings.mlr.press/v267/heddes25a.html)
- [arXiv v2の表と手法](https://arxiv.org/html/2502.06785v2)

[分野別索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
