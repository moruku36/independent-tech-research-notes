# Event-Driven ML Pipeline Orchestration for Manufacturing: An AWS Industry Experience

[English](2026-manufacturing-ml-event-pipeline.md) | [テーマ索引](README.ja.md)

- **原文:** [arXiv:2610.06890v1](https://arxiv.org/html/2610.06890v1)、IC2E 2026採択の企業事例、2026年9月24日投稿。
- **著者:** Zhengyang “Cissy” Gu、Thomas Cook、Fredaljohn Rohrbaugh、Joseph E. Hernandez、Chris Couch。
- **確認範囲:** 本文主要部分、費用表とシミュレーション。費用の独立監査・再現は未実施。

## 概要
Liveline Technologiesが製造業向けのAWS上のGPU学習基盤を報告する。実運用の費用報告と、障害時のジョブ処理を調べる離散イベントシミュレーションは別の根拠である。著者は同社所属で、研究は同社から資金提供を受けている。

## 方法と結果
3年間に複数工場で4万件超の学習ジョブを扱ったと報告する。SQSとデッドレターキュー、同時実行数2のLambdaによる受付制御、再利用するECS/EC2 GPUワーカー、Fargate上のConductor、Terraformを組み合わせる。1拠点あたり月額は常時稼働の比較例3,200ドルに対し、オンデマンドのみ910ドル、Spotとチェックポイントを使うLPP構成760ドルで、それぞれ約72%、76%削減と報告する。

別の52週間・GPU 2基・2,077ジョブのシミュレーションでは、デッドレターキューなしで単純に再試行を尽くす方式は1,342ジョブを失い、Step Functionsと提案方式は損失ゼロだった。これは実際の運用損失ではなく、設定した条件でのシミュレーション結果である。

## 実務への応用
自宅ラボやAWS環境では、キューによる受付制御、ワーカー再利用、失敗ジョブの退避、チェックポイントを検討できる。待ち時間、GPU利用率、完了率、総費用を実負荷で測る。AzureやGCPへの展開は別途検証が必要。

## 限界
単一企業の自己報告とモデル化した負荷であり、シミュレーションはネットワークの揺らぎ、スロットリング、AZ障害を含まない。費用や耐障害性を他環境にそのまま一般化できない。
