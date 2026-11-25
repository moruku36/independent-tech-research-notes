**日本語** | [English](2026-sakana-agentic-scientist.md)

# The Agentic Scientistによる研究の並列実行と証拠管理

## 概要

- **何についてのものか** コーディングエージェントを使って計算研究を進めるSakana AIの実行基盤。
- **何を述べているか** 並列探索、ベースライン・要素除去実験、証拠の集約、論文執筆を統括する。
- **留意点** 自動のルーブリック評価は代理指標。新規性と独立再現には追加の確認が要る。

## 実務向けの読み解き（6行）

- タスクの契約で、候補プログラムの形式と評価手順を定める。
- 並列ワーカーが別の作業領域で仮説を試し、要点を共有する。
- 案の検証完了と、最良プログラムの更新には別の受入条件がある。
- 選んだ結果を、追加実験と報告の根拠にする。
- 研究ハーネスへの応用案は、仮説、コードの版、評価、根拠ファイルを結ぶ記録。
- 著者はタスクの自動作成の不完全さと、初期の文献探索の不足を限界として挙げる。

## 書誌・確認範囲

Robert Tjarko Lange、Luca Grillotti、Yutaro Yamada、Rujikorn Charakorn、David Ha。arXiv:2610.18933v1、2026-10-13。2026-11-12 JSTに§3・§5・§8を部分確認。実装の実行と追試は未実施。

## 方法・証拠・限界

事例研究と、人が用意した5課題の計70キャンペーンを報告する。AIによる論文評価は探索スコアを補う指標。人と共作した論文1件の学会採択は別種の証拠となる。著者も独立再現と新規性評価の改善を課題に挙げる。

## Sakana AIの講演（2026-11-25）

2026-11-26 JSTに、公式動画の説明欄、チャプター、該当箇所の文字起こしを確認。同じプレプリントに対応する講演で、共同研究の進め方と図の生成工程を補足している。

- [9:25～12:36](https://www.youtube.com/watch?v=JKcPclh4lEo&t=565s) — 固定した評価指標の改善と、新しい研究の方向性を見つけることを区別する。任意の準備工程で初期プログラムと評価関数を用意し、並列探索の結果をベースライン比較、要素除去実験、分析、執筆・レビューにつなぐ。
- [12:37～16:54](https://www.youtube.com/watch?v=JKcPclh4lEo&t=757s) — ALIFE 2026の口頭発表に採択された事例では、人が初期方針と制約を決め、強化学習環境を整え、結果・引用・主張を検証した。エージェントは実験と図・本文の下書きを担当した。
- [16:55～19:42](https://www.youtube.com/watch?v=JKcPclh4lEo&t=1015s) — Doc-to-LoRAでは、質問に応じてLoRAアダプターを統合する案を探索した。報告された結果は文中の複数の情報を探す検索課題に基づき、一般の長文への転用は未確認。
- [19:43～20:53](https://www.youtube.com/watch?v=JKcPclh4lEo&t=1183s) — 見つけた解法の性能と、AIによる原稿の評価点の相関を報告している。点数は代理指標で、ALIFE採択は人との共同研究1件の結果。
- [20:54～23:12](https://www.youtube.com/watch?v=JKcPclh4lEo&t=1254s) — AutoIllustrateは編集可能なdraw.ioの元図と、見た目を整えた画像を出力する。研究者は元図を確認し、修正できる。

## 関連資料

- [The AI Scientist](2024-sakana-ai-scientist.ja.md)
- [Organon](2026-organon-scientific-discovery.ja.md)

## 無料の確認計画・活用状態

提案・未実施。小さな決定的実験で仮説を先に書き、探索に使わない最終テストを確保する。失敗した試行も残し、固定のベースラインと比較する。次はタスク契約、計算予算、評価器の独立性を確認する。

## 一次資料

- [arXiv record](https://arxiv.org/abs/2610.18933)
- [Inspected v1](https://arxiv.org/html/2610.18933v1)
- [Linked implementation](https://github.com/SakanaAI/AI-Scientist-v3)
- [Sakana AIの講演とチャプター](https://www.youtube.com/watch?v=JKcPclh4lEo)
- [Sakana AIの公式プロジェクト解説](https://pub.sakana.ai/agentic-scientist/)
- [共同研究事例の論文 Diffusing Blame](https://arxiv.org/abs/2606.31700)
- [AutoIllustrateの公式リポジトリ](https://github.com/SakanaAI/autoillustrate)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
