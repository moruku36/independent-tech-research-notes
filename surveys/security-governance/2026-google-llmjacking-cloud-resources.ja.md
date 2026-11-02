**日本語** | [English](2026-google-llmjacking-cloud-resources.md)

# Google／Mandiant：クラウドのLLM資源を盗用するLLMJacking

## 概要
- **何か**：Google Threat Intelligence GroupとMandiantによるインシデント分析記事。
- **報告**：漏えい・窃取されたクラウド認証情報などからLLM利用枠を悪用し、第三者に再販する事例を報告する。
- **注意**：企業が対応した事例の報告であり、被害規模や頻度を業界全体へ一般化できない。

## 資料と確認範囲
Christopher Romano、Codi Starks、Garrett Mahoney、John Wolfram、Josh Murchie、K Singh、Mathew Potaczek、Mike Lombardi、Rik Dolfing、[The Rise of LLMJacking: How Threat Actors Monetize Compromised Cloud and Model Resources](https://cloud.google.com/blog/topics/threat-intelligence/llmjacking-monetizing-compromised-cloud-models/?hl=en)、Google Threat Intelligence Group／Mandiant、2026年11月2日公開。2026年11月3日（日本時間）に、指定URLの直接取得は内部エラーだったが、同じ公式ページの検索結果に表示された本文の主要部分を確認。全ページの表示・図・ルールの網羅確認、独立検証は未実施。

## 何が起きたか
Mandiantは2026年に複数の組織で、攻撃者がクラウドやLLMの認証情報を得て、モデルの利用枠を不正利用したと報告する。初期侵入後に権限や鍵を追加し、推論の大量実行やGPUの確保を行う例がある。GTIGは盗用した利用枠を中継・再販する「LLM Mixer」の存在も報告する。これは同社の観測・分析であり、独立した全体統計ではない。

## 影響と注意
同社は個別事例で1日10万米ドルを超える不正な利用料金、複数日に累計100万米ドルに達した組織もあったと述べる。対象数や分母は示されておらず、一般的な損害額とは扱わない。少量のAPI呼び出しで盗んだ鍵を検証する行動も報告されている。将来の増加や犯行分業については同社の見通しと分析であり、確定した予測ではない。

## 実務への応用案
- AWS・Azure・GCPやLLMゲートウェイで、サービスアカウント、APIキー、サービスの新規有効化と権限変更を棚卸し・監視する。
- 鍵の環境別分離、最小権限、短命な認証情報、不要な公開エンドポイントの閉鎖を検討する。
- 使用量や課金の急増だけでなく、少量の不審な検証アクセスもログで調べる。アラートは支出を止める保証ではなく、実際の上限・クォータ・停止方法を個別に確認する。
- 不正利用時のキー失効、セッション遮断、証拠保全、課金・影響調査を事前に準備する。

これらは記事を踏まえた防御提案であり、ユーザー環境への導入・有効性は未検証。

[セキュリティ・ガバナンス索引](README.ja.md)
