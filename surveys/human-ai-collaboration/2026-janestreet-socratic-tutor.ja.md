**日本語** | [English](2026-janestreet-socratic-tutor.md)

# Jane StreetのSocratic Tutorスキル設計

## 概要

- **何についてのものか** ソクラテス式の個別指導を定める公開の指示ファイル。
- **何を述べているか** 診断、下位技能ごとの段階、問いかけ、間隔を置いた想起、最終評価を指定する。
- **留意点** 手順を定義したファイルで、学習効果の対照実験は示していない。

## 実務向けの読み解き（6行）

- 継続した指導を明示的に求めた場合を対象とする設計。
- 短い診断で、下位技能ごとの現在地を置く。
- 指導ループでは、一度に1問ずつ尋ねる。
- 段階を上げる際は、想起を含む独立した確認を求める。
- 応用の確認案は、その場の正答に加えて後日の定着も測ること。
- 今回は資料として読解し、インストールや指導の試行は未実施。

## 書誌・確認範囲

Jane Street agent_skillsのsocratic-tutor/SKILL.md。2026-11-13 JSTにcommit 7c6715c29548a3b39d4a9545c698ee4fd17a7213（2026-11-03）を確認。確認時のmasterと本文が一致した。

## 内容・証拠・限界

短い説明と継続指導を区別する設計。再確認、難度変更、状態保存の操作も含む。読んだファイルには、学習者の調査や習熟度尺度の妥当性検証は添付されていない。

## 関連資料

- [好奇心・メタ認知](2026-curiosity-metacognition-ai-learning.ja.md)

## 無料の確認計画・活用状態

提案・未実施。小さな概念集合と後日の独立した問いを用意し、同程度の時間で指導と固定説明を比較する。次は想起と応用の採点方法を利用前に定める。

## 出典

- [Submitted master file](https://github.com/janestreet/agent_skills/blob/master/socratic-tutor/SKILL.md)
- [Inspected revision](https://github.com/janestreet/agent_skills/blob/7c6715c29548a3b39d4a9545c698ee4fd17a7213/socratic-tutor/SKILL.md)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
