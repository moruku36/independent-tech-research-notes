**日本語** | [English](2026-aws-cognito-plus-availability-sla.md)

# Amazon Cognito Plusの99.99% SLAとアプリ側の可用性計測

## 概要

- Cognito Plusユーザープールの月間可用性に関するサービスコミットメントの引き上げを解説したAWS公式記事。
- 2026-11-01から、Plusはリージョン・請求月ごとに99.99%。EssentialsとLiteは99.9%を維持する。
- SLAは対象のエラーと除外条件を規定している。記事の過去実績はリージョンをまたぐリクエスト数加重の集計値。

## 実務向け6行

- 既存のPlusユーザープールには、2026-11-01から99.99%のサービスコミットメントが自動適用される。
- リージョンごとに、HTTP 500・503をエラーとする5分単位の可用性を平均する。リクエストがない区間は100%と扱う。
- 30日間を時間に換算すると停止予算の目安は4.32分。契約上の値はリクエスト計測と除外条件で決まる。
- AWS公表の集計では、2025年11月から2026年10月までの12か月のうち10か月で99.99%以上だった。
- アプリでは、クライアントや後続処理まで含めたサインイン成功率もCognitoのSLAと並べて計測する。
- APIやCLIでプランを変更する前に既存設定を取得し、更新に含める。省略したパラメーターは既定値に戻る可能性がある。

## 書誌・確認範囲

- 確認状態は一次資料確認済み。2026-11-28にAWS公式ブログの英語版と公式SLAを確認。
- 書誌情報。Brian Song、Chris Simmons、*Planning for 99.99 percent availability with the Amazon Cognito Plus feature plan*、AWS Security Blog、2026-11-25。
- 一次資料。[AWS Security Blog英語版](https://aws.amazon.com/blogs/security/planning-for-99-99-percent-availability-with-the-amazon-cognito-plus-feature-plan/) · [Amazon Cognito SLA](https://aws.amazon.com/cognito/sla/)。

## 計測とサービスクレジット

サービスコミットメントはリージョン別・請求月単位。SLAには適用条件、申請方法、クレジット率、除外条件がある。停止した時間の合計だけでは契約上の値を求められない。

## 過去実績の範囲

新しい基準に届かなかったのは、2026年1月の99.988%と3月の99.979%。AWSは各リージョンの値をリクエスト数で加重した。個別アカウントやリージョンの体感可用性は集計値と異なりうる。

## 関連ノート

[AWS Well-Architected 2026のクラウド基盤とワークロード](2026-aws-well-architected-foundations-workloads.ja.md)は、共通統制とワークロードの範囲を扱う。Cognitoは、構成要素の契約とアプリ全体の可用性目標で計測範囲が異なる例。

## 無料でできる確認案

表計算で、5分間にリクエストがない区間、500・503が混ざる区間、クライアント側でログインが失敗する区間を架空の数字で作る。SLAに沿った集計と、条件を明示したアプリのサインイン成功率を計算する。活用状態は提案。実環境の可用性とプラン変更は未検証。
