**日本語** | [English](2025-sakana-adaptive-branching-mcts.md)

# AB-MCTS：新しい候補と既存案の改善を配分する探索

## 概要

- 研究記事と対応論文：候補を広げるか、既存案を深めるかを適応的に選ぶ推論時探索。
- 外部評価とThompson Samplingで探索を配分し、Multi-LLM版では使うモデルも選ぶ。
- ARC-AGI-2で候補を発見できるPass@250と、2解を提出するPass@2では結果が大きく異なる。

## 実務向けの読み解き（7行）

- AB-MCTSは、新しい解を増やすか、既存の解を直すかを探索中に選ぶ。
- 外部評価の結果を使い、Thompson Samplingで次に試す枝を決める。
- Multi-LLM版は、どのモデルへ次の生成を任せるかも選択する。
- ARC-AGI-2の120問・最大250回の生成で、30%超の課題に正解候補を見つけたと報告する。
- 2つの最終解を選ぶ暫定的な評価では19.2%で、候補の発見と選別の差がある。
- 本ノートの応用案：同じ予算で独立生成・逐次修正・探索を比べ、最終提出物も評価する。
- 評価器の質と呼び出し単価・遅延に依存し、全課題で常に優位とはいえない。

## 書誌・確認範囲

- 指定記事：Inference-Time Scaling and Collective Intelligence for Frontier AI、Sakana AI、2025-07-01。
- 対応論文：Wider or Deeper? Scaling LLM Inference-Time Compute with Adaptive Branching Tree Search。Yuichi Inoue、Kou Misaki、Yuki Imajuku、So Kuroki、Taishi Nakamura、Takuya Akiba。
- arXiv:2503.04412v5（2025-11-07、初版2025-03-06）。arXivのコメント欄はNeurIPS 2025 spotlight採択と記載。会場側の独立照合は未実施。
- 2026-11-07 JST確認。記事本文、一次HTMLの方式、表1、限界、付録DのMulti-LLM・ARC-AGI-2評価を部分確認。TreeQuestと実験コードは未実行。状態：部分読了／再現未実施。

## 研究の問い

LLMの推論予算を、新候補の生成、既存案の改善、異なるモデルの利用へどう配分すればよいか。

## 手法・データ・比較条件

AB-MCTSは外部スコアをもとに、探索木の幅と深さをThompson Samplingで調整する。論文では独立反復生成、逐次改善、標準MCTSと比較。Multi-LLM版はモデル選択を追加し、o4-mini、Gemini-2.5-Pro、DeepSeek-R1-0528を使うARC-AGI-2の例を示す。

## 主張と証拠

ARC-AGI-2公開評価120問、1問最大250回の生成で、単一o4-miniの反復生成は約23%、AB-MCTSは27.5%、Multi-LLMは30%超の課題で正解候補を発見したと報告する（記事・付録D）。これはPass@250の探索能力。単純な規則で最終2解を選ぶ暫定評価のPass@2は19.2%。論文表1のARC-AGIでは反復生成が首位であり、全条件でAB-MCTSが最良という結果ではない。

## 限界・妥当性への脅威

信頼できる外部評価器を仮定する。例題への適合が未知のテストの正解を保証しない。候補群に正解が存在しても、それを選べるとは限らない。呼び出し回数を揃えてもモデルごとのトークン単価・時間は揃わず、研究時点のモデルと課題に依存する。記事の初期実験と論文本文の別ベンチマークを混同しない。

## 関連研究との比較

[RIVET](2026-rivet-multiturn-llm-routing.ja.md)は各ターンのモデル選択を学習し、本手法は解候補の探索と評価フィードバックを使う。[簡素なML開発ハーネス](../coding-agents/2026-ml-engineering-minimal-harness.ja.md)と比較し、探索追加の効果を同一条件で測る必要がある。これらは直接比較した実験ではない。

## 無料で行える確認計画・活用状態

提案・未実施。公開ログから、候補群の最高得点と実際に選んだ提出物の得点を別々に集計する。小さな公開課題で試す場合は生成数と最終提出数を固定し、無料の既存環境で可能な範囲に限る。活用状態：提案。

## 未確認点・次の確認

公開実装の版、評価器と最終解選択規則、金額・トークン・待ち時間で揃えた比較を次に確認する。

## 一次資料

- [指定された研究記事](https://sakana.ai/ab-mcts/)
- [対応論文の書誌](https://arxiv.org/abs/2503.04412)
- [確認した論文版](https://arxiv.org/html/2503.04412v5)
- [公開コード（未実行）](https://github.com/SakanaAI/treequest)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
