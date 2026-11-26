**日本語** | [English](2023-react-reasoning-and-acting.md)

# ReAct：推論・操作・観測を交互に使うプロンプト設計

## 概要

- 外部環境とやり取りする言語モデル向けのプロンプト手法を提案したICLR論文。
- ReActは推論の記述、操作、操作結果の観測を組み合わせる。質問応答、事実確認、操作を伴う課題で効果は異なる。
- 結果は当時のモデル、操作環境、プロンプト例に依存する。記録は誤りの調査に役立ち、記録自体にも誤りがあり得る。

## 実務向け6行

- 推論で文脈を更新し、操作で情報を取得したり環境を変えたりして、観測結果を次の判断に使う。
- FEVERの正解率はReActが60.9%、推論のみのCoTが56.3%。HotpotQAの完全一致率はそれぞれ27.4%、29.4%。
- ReActと複数の推論結果から答えを選ぶCoT-SCを組み合わせると、両課題でReAct単体より改善した。良い順序は課題で異なった。
- ALFWorldでは6条件中の最良成績がReAct 71%、Act 45%。模擬サイトのWebShopでは成功率がそれぞれ40.0%、30.1%。
- 論文は、検索で情報が得られない例や操作を繰り返す例を報告している。最終回答と合わせてツール出力と記録を確認できる。
- 応用案。読み取り専用のツールと予算をそろえて方式を比べ、取得した根拠、完了、失敗を記録する。

## 書誌・確認範囲

Shunyu Yao、Jeffrey Zhao、Dian Yu、Nan Du、Izhak Shafran、Karthik Narasimhan、Yuan Cao。ICLR 2023、arXiv:2210.03629v3（2023年3月10日）。2026年11月27日（JST）に§2〜4と表1〜4を確認。追試は未実施。

## 根拠と限界

- HotpotQAとFEVERはPaLM-540Bを使用し、質問や主張だけを最初に渡す。ReActは機能を限定したWikipediaインターフェースを利用できる。両課題の指標は完全一致率と分類正解率。
- 表1ではReAct→CoT-SCでHotpotQA 35.1%、CoT-SC→ReActでFEVER 64.6%。ALFWorldは6つのプロンプト条件の最良値で、WebShopの成功は指定項目をすべて満たした場合を指す。
- 結果は利用できるツールとプロンプトの構成に依存する。検索が空または不十分だと進行が止まりやすく、読める記録にも誤った推論は残り得る。

## 応用・無料の確認案

提案・未試行。正解が分かる少数の文書をローカルに置き、同じ検索条件で回答のみ、操作のみ、推論と操作を組み合わせる条件を比較する。根拠文書と、根拠不足や同じ操作の繰り返しを記録する。

## 関連ノート

- [SWE-agentとエージェント向け操作環境](2024-swe-agent-computer-interface.ja.md)
- [Claude Codeの検証の実践](2026-claude-code-verification-practices.ja.md)

## 出典

- [arXiv v3の書誌](https://arxiv.org/abs/2210.03629v3)
- [確認したv3本文](https://arxiv.org/html/2210.03629v3)
- [ICLR 2023](https://openreview.net/forum?id=WE_vluYUL-X)

[分野別索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
