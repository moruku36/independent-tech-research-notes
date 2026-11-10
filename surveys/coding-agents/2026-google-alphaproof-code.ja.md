**日本語** | [English](2026-google-alphaproof-code.md)

# AlphaProof Codeによるlibsignalの機械検証

## 概要

- **何についてのものか** libsignalを対象にしたGoogle DeepMindのエージェント支援形式検証。
- **何を述べているか** 人が承認した仕様、AArch64機械コードのモデル、Leanの証明検査を通じ、選んだ性質をコンパイル済み成果物に結び付ける。
- **留意点** 保証の範囲は対象バイナリ、形式仕様、信頼する前提に依存する。

## 実務向けの読み解き（6行）

- プロトコルの特定の性質を、コンパイル済みコードについて証明できるかを問う。
- エージェントが証明を試みる前に、専門家がLeanの仕様の意味を確認する。
- 受入段階で、承認済みの命題に対する証明をLeanで検査する。
- 技術論文は、モデル化した条件でPQXDHハンドシェイクとTriple Ratchetの特定の性質を示す。
- 研究ハーネスへの応用案は、独立した検証器が受け入れた仕様と成果物を版ごとに記録すること。
- 証明は前提の下で命題を成立させる。仕様の忠実性と網羅性はレビューで確かめる。

## 書誌・確認範囲

Pushmeet Kohli、Swarat Chaudhuri、Google DeepMind発表記事、2026-11-10。技術論文はSwarat Chaudhuri、Andrew Ferraiuoloほか。2026-11-11 JSTに発表記事と技術論文の要旨、検証手順、適用範囲を確認。

## 手法・証拠・限界

著者らは約650万行の検査済みLean証明コードと、約2.6万行の信頼する仕様・機械語意味論を報告する。これらは今回の成果物の規模を示す値で、証明・レビューの工数は対象によって異なる。対象は特定のlibsignalビルドと実行モデル上の性質で、保証はモデルと前提に依存する。

## 関連研究・記事

- [AIによる量子プログラム発見と形式検証](2026-formally-verified-quantum-discovery.ja.md)
- [Neuro-Formal Verification](2026-neuro-formal-verification.ja.md)

## 無料の確認計画・活用状態

提案・未実施。自分が管理する小さな決定的プログラムで不変条件を1つ選び、仕様を版固定する。仕様の確認者、想定入力、コードの版、受入条件を残す。次は技術論文の信頼基盤と適用範囲の節を精読する。本ノートでの証明の再実行は未実施。

## 出典

- [DeepMind announcement](https://deepmind.google/blog/introducing-alphaproof-code/)
- [Technical report](https://google-deepmind.github.io/code-verification/)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
