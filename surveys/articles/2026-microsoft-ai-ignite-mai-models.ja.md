**日本語** | [English](2026-microsoft-ai-ignite-mai-models.md)

# Ignite 2026のMicrosoft AI：モデル評価・料金・提供条件

## 概要

- **何についてのものか**：Ignite 2026でMicrosoft AIが発表したMAIモデル群、モデルの振り分け、ライセンスによる展開についての公式記事。
- **何を述べているか**：用途ごとの評価成績と低い費用を報告し、個別発表で料金の計算条件や提供段階を示している。
- **留意点**：コーディングの費用比較はMAI側の割引価格を使用。評価、プレビュー、顧客事例はそれぞれ条件付きの情報。

## 実務向け6行

- 企業で繰り返し発生する作業を、用途別のモデルでどこまで低コストで処理できるかを扱う発表。
- Microsoftによると、MAI Code 2は4つのコーディングベンチマークでGPT-6.1 Sol比98%の成績、40%の費用だった。
- 比較には最大の推論設定とMAI側の50%割引価格を使用。4件中3件はサブエージェントを無効にしたGitHub Copilot CLIで評価した。
- Image 2.7はパブリックプレビュー。Realtime 1は音声と推論が別課金で、Foundryでは限定アクセスのプレビュー。
- モデルの振り分けなどに使うDecision 1.1は一般提供。顧客のAzure環境で使うLicensed Weightsは、Frontier Companyを通じて今後提供予定とされた。
- 応用案は、代表タスクの採用できた変更1件あたりの費用を、料金・再試行・人のレビュー時間・利用条件とあわせて測ること。

## 書誌・確認範囲

Microsoft AI、2026年11月17日公開。2026年11月21日（JST）に指定記事と下記の個別発表の該当箇所を確認。提供段階と料金は発表時点の記載。ベンチマーク、顧客事例、展開時の動作の独立検証は未実施。

## 根拠と限界

| 対象 | 発表時点のMicrosoftの報告 | 読むときの条件 |
| --- | --- | --- |
| MAI Code 2・Code 2 Flash | Code 2は4ベンチマークで、GPT-6.1 Sol比で得点98%・費用40%、Claude Opus 5.5比で得点96%・費用5%。Flashは3ベンチマークでGPT-6 Luna、Claude Haiku 5.5と同程度の得点で、費用はそれぞれ65%、20%。 | 比率の分母は各比較モデル。最大の推論設定と、MAI側の50%割引価格を使用。DeepSWE 1.1、TerminalBench 2.1、SWE-AtlasはMicrosoftのMSBenchで、サブエージェントを無効にしたGitHub Copilot CLIで実行。Code 2はArtificial AnalysisのFrontierCode v1.1を加えた。両方をGitHub Copilotで提供し、FlashはFoundryで限定プレビュー。 |
| MAI Image 2.7・Flash | Image 2.7はArtificial Analysisの画像編集で1位。Foundryでの概算は1,000枚あたり通常版35米ドル、Flash 10米ドル。 | 両方をパブリックプレビューで発表。順位は画像編集のもので、費用は画像リクエストの条件による。 |
| MAI Realtime 1・Dragon Copilot Transcribe | Realtime 1の音声料金は1分あたり0.01米ドルから。Dragon Copilot TranscribeはMAI Transcribe 2を使用し、多言語の文字起こしの誤りが減ったと報告。 | Realtime 1は推論を別に課金し、100万入力トークンあたり1米ドル、100万出力トークンあたり5米ドル。文字起こしは提供元が報告した業務上の結果。 |
| Microsoft-Decision-1.1・MAI Licensed Weights | 振り分けや分類向けのDecision 1.1はFoundryで一般提供され、OpenRouterとVercelでも提供。Licensed Weightsは顧客のAzure環境での展開・アクセス制御・追加学習を想定。 | 振り分けの成績は課題や判断を保留する条件に依存。ライセンス提供はFrontier Companyを通じて今後開始と発表。個別の契約条件は今回の確認範囲外。 |
| MAI Cyber 2 Flash・Maia 200 | セキュリティ防御チーム向けのモデルと、Microsoftのモデルを本番で動かしているMaia 200アクセラレーターを紹介。 | セキュリティ評価は発表で測った構成の結果。アクセラレーターの電力効率はワットあたりのトークン数で測り、作業1件を完了する費用とは別の指標。 |

費用の比率は選定されたベンチマークでの集計。実際のリポジトリで採用できる変更1件あたりの費用は、採用率、再試行、人のレビュー時間でも変わる。評価成績、利用実績、提供段階はそれぞれ異なる判断材料になる。

## 応用・無料の確認案

提案。架空または公開の小さなコーディング課題に、共通のテストとレビュー条件を設定する。成功・再試行・推論料金・レビュー時間から採用できた変更1件あたりの費用を計算する手元の表を作り、製品試用の前に仮の金額で割引時と通常料金の条件を比べる。

## 関連ノート

- [企業AI基盤を扱うMicrosoftのIgnite基調講演](2026-microsoft-ignite-frontier-ecosystem.ja.md)
- [展開と運用を扱うAzureのIgnite発表](2026-azure-ignite-platform-announcements.ja.md)

## 出典

- [Microsoft AIの発表概要](https://microsoft.ai/news/microsoft-ignite-2026/)
- [Code 2・Flashの評価条件](https://microsoft.ai/news/introducing-mai-code-2-and-mai-code-2-flash/)
- [Image 2.7の発表とプレビュー](https://microsoft.ai/news/introducing-mai-image-2-7/)
- [Realtime 1の課金条件](https://microsoft.ai/news/introducing-mai-realtime-1/)
- [Decision 1.1の提供と評価](https://commandline.microsoft.com/microsoft-decision-model-ga/)
- [Licensed Weightsの発表](https://microsoft.ai/news/introducing-mai-licensed-weights/)

[テーマ索引](README.ja.md) · [全読書一覧](../../docs/reading-list.ja.md)
