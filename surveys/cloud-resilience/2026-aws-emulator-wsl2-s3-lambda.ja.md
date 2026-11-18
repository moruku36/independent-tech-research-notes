**日本語** | [English](2026-aws-emulator-wsl2-s3-lambda.md)

# WSL2上のAWS Emulatorで確かめたS3とLambdaの挙動

## 概要

- **何についてのものか** Windows PCでAWS Emulatorを試した実践記事。
- **何を述べているか** WSL2上でS3の書き込み・読み戻しと、Python Lambdaの実行を報告。
- **留意点** テストでは、存在しないIAMロールでも関数を作成・実行できた。

## 実務向け6行

- 著者はWSL2のUbuntuにLinuxパッケージ1.0.500を導入した。
- AWS CLIはローカル接続先と専用の認証情報を使った。
- S3ではオブジェクトを書き込んで中身を読み戻した。
- LambdaはPythonコードを実行し、期待した値を返した。
- アプリの基本動作を確かめるスモークテストに応用できる。
- ローカルの成功では未確認のIAM認可を別に検証する。

## 書誌・確認範囲

N-Kyo、Qiita、2026年11月18日公開。11月19日 JSTにブラウザで記事本文を読み、AWS公式の概要と再現性の文書を確認。

## 根拠と限界

実行例は単一環境の小規模な2経路。AWSの文書ではWindows向けにDocker、Linux向けにパッケージを案内しており、WSL2への導入は著者が選んだ方法。AWSも、ポリシー評価の違いと、特にデータプレーンでの操作ごとの再現範囲の差を明記している。

## 応用・無料の確認案

提案／未試行。オブジェクトの往復、関数の出力、権限エラーを分けた試験表を作り、各項目をどこで確認できるかを記録する。

活用状態は提案。今回の読書ノート作成では実環境での再現や導入を行っていない。

## 関連ノート

- [リポジトリ内の関連ノート](2026-aws-emulator-local-testing.ja.md)

## 出典

- [Qiita article](https://qiita.com/N-Kyo/items/a111d174a751506790e2)
- [AWS Emulator overview](https://docs.aws.amazon.com/emulator/latest/userguide/what-is-service.html)
- [AWS fidelity documentation](https://docs.aws.amazon.com/emulator/latest/userguide/fidelity.html)

[テーマ索引](README.ja.md) · [読書一覧](../../docs/reading-list.ja.md)
