**日本語** | [English](2026-npaka-ubuntu-security-layers.md)

# Ubuntuの標準セキュリティ：Desktop・Serverとエージェントの隔離条件

- npakaによるUbuntuのセキュリティ入門記事。26.04 LTSを軸にDesktopとServerの攻撃経路、標準機能、保守を整理する。
- AppArmorのプロファイル、Snapの制限モード、暗号化やFirewallの有効状態によって、実際の保護範囲が変わる。
- 防御率やOS間の優劣を測った論文ではない。通常ユーザーで動くAIエージェントにも、ファイル・認証情報・通信の境界設計が必要になる。

## 実務向けの読み解き（7行）

- Desktopの偽アプリや認証情報窃取と、Serverの公開サービス・SSH・設定ミスを分けて考える。
- AppArmorが有効でも、対象プロセスに強制される適切なプロファイルがなければ同じ隔離にはならない。
- SnapはStrict・Classic・Devmodeで制限が異なり、配布形式だけで安全と判断しない。
- LUKSやTPMによる保存データの保護と、起動後にユーザー権限で読める情報を区別する。
- UFWの設定だけでDockerの公開ポートやエージェントの通信先まで制限できるとは考えない。
- OSの保守、APT、pip／npm、コンテナイメージを別々に追跡する運用を検討する。
- 以下の棚卸しは本ノートの提案で、端末設定の変更・更新・攻撃実験は行っていない。

## 書誌・確認状況

- 指定記事：Ubuntuのセキュリティの仕組み - 標準機能と安全に使うための対策
- 著者：npaka。公開：2026-11-08 21:21（記事表示、JST）。
- 種別：個人の解説記事。学術論文・比較ベンチマークではない。DOI／arXiv IDなし。
- 確認日：2026-11-08 JST。閲覧時点のWeb本文。固定版番号なし。
- 状態：指定本文を末尾まで確認。Canonical／Snap／Dockerの公式資料で主要機能、26.04の変更、保守範囲、2件の脆弱性事例を選択的に照合。
- 未実施：Ubuntu実機の状態確認、設定変更、ソフトウェア更新、マルウェア・脆弱性の再現、防御率測定。

## 問い・方法・比較条件

Ubuntuの標準機能が何を守り、どこに追加の設定や継続保守が必要かを説明する。Desktopでは利用者が動かすコード、Serverでは外部に公開するサービスを主な入口として整理するが、両者の脅威は排他的ではない。

記事は機能と事例をまとめた解説であり、同じ攻撃セット、設定、ハードウェアによる実験ではない。本ノートでは保護の成立条件を公式資料と照合し、エージェント運用への応用を別の提案として記す。

## 主張と根拠

| 層 | 記事が扱う機能 | 適用条件・限界 |
|---|---|---|
| 起動・権限 | Secure Boot、ユーザー／グループ、sudo | 起動の署名確認と実行後のアクセス権は別。root以外でも読めるファイルはある |
| アプリ隔離 | AppArmor、Snap | プロファイルとモード、接続されたインターフェースを確認する |
| 更新・保守 | APT、unattended-upgrades、Ubuntu Pro | リリース、パッケージの区分、導入元により対象が異なる |
| 保存データ | LUKS、TPM、認証情報の管理 | 暗号化を選択したか、対応ハードウェアか、ディスクが解錠済みかが重要 |
| 通信 | UFW、TLS、SSH、VPN | ホストの規則、コンテナの公開経路、通信路の暗号化を分ける |

AppArmorはアプリごとのポリシーで制限する。enforceとcomplainを区別し、プロファイルが読み込まれていることと、意図した拒否が強制されることを同一視しない。SnapのStrictはAppArmor・seccomp・名前空間などを使い、許可されたインターフェースを通じてアクセスする。Classicは従来型パッケージに近い広いアクセス、Devmodeは開発用で強制を緩める。Snap Storeに存在することは、すべて同じ制限や安全性の保証ではない。

CanonicalのUFW説明は初期状態が無効とする。ただし実環境の状態は未確認であり、UFWが無効だからホストやクラウドに他の通信制御がないとも言えない。Docker公式資料は、公開したコンテナポートの通信がUFWの通常の処理経路より前で転送される問題を説明する。「UFW有効」だけで公開範囲を判定しない。

### 26.04 LTSと保守

Canonicalは26.04 LTSでTPMに基づくDesktopの全ディスク暗号化を正式な機能として説明するが、ハードウェア・構成の制約は残る。これをすべてのServerや既存インストールへ自動適用される機能とは扱わない。sudo-rsは26.04で標準だが、公式のLTS向け変更一覧では25.10で追加された変更とされる。「26.04で初めて登場」とは書かない。

AppArmorのユーザー向け許可プロンプトは公式記事でも実験的かつ標準無効とされる。新しい暗号ライブラリのPQC対応も、すべての接続でPQCが交渉されることを意味しない。

確認日の公式ライフサイクル表では26.04 LTSの標準保守は2031年5月まで。Pro／Legacyは保守範囲と期間を拡張するが、すべての外部依存を保守する契約ではない。自動更新も対象の導入元・設定によるため、pip、npm、外部リポジトリ、コンテナイメージまでAPT任せにしない。

### 記事の事例と照合

- **regreSSHion（CVE-2024-6387）**：Canonicalは2024年7月1日に修正を提供。22.04 LTS・23.10・24.04 LTSが修正対象だった。実際の悪用可能性にはアーキテクチャや追加パッチによる条件があり、すべてのSSH公開端末で無条件に成立する攻撃とは記さない。
- **XZ（CVE-2024-3094）**：公式CVEページでは公開済みUbuntuリリースは非該当。問題の版はnoble-proposedに存在したが、通常のリリースへ移行する前に除去された。Ubuntu安定版が一律に侵害された事例とは扱わない。

## 限界

強弱評価は定性的な目安で、Mac・Windows・Ubuntuの順位を示す結果ではない。Desktop／Server、VM／コンテナ、リリース、イメージ、プロファイル、権限、ポート公開、保守契約を揃えずに防御の効果を比較できない。

署名された配布物や更新済みOSでも、実行を許可したコードが読める情報や、外部命令に従うエージェントの行動は別途考える必要がある。rootを使わないことや、コンテナ内で動かすことだけで隔離が完了したとは判断しない。

## 関連ノートと応用案

- [Macの標準セキュリティ](2026-npaka-macos-security-layers.ja.md)、[Windowsの標準セキュリティ](2026-npaka-windows-security-layers.ja.md)：各OSの機能の役割と適用範囲を対応付ける。
- [Kubernetes上の自律エージェントの多層防御](2026-kubernetes-autonomous-agent-containment.ja.md)：権限・作業領域・通信を独立に制御する設計と比較する。

エージェント用の実行ユーザー、書き込み可能領域、秘密情報の置き場所、ホスト共有、公開ポート、送信先を一覧にする案がある。AppArmorの対象とモードも含め、実際にどの境界が強制されるかを確認する。これは本ノートの応用提案で、記事が測った防御効果ではない。

## 無料でできる確認案（未実施）

Ubuntu環境がある場合、OS版・Desktop／Server・VM／コンテナの区分、AppArmorの対象とモード、Snapのモードと接続、暗号化の表示、UFW／公開ポート、更新の導入元を読み取り専用で記録する。

SSH接続中のFirewall有効化、保護の無効化、パッケージ更新、再起動はこの棚卸しに含めない。鍵・トークン・復旧情報・個人ファイルを報告へ貼り付けない。

- 活用状態：提案のみ。実機検証・実装採用なし。
- 次の確認：実行環境ごとのプロファイル、Dockerとホストの通信経路、依存ソフトの保守対象。

## 出典

- 指定解説：[npaka](https://note.com/npaka/n/nb718fa9cb373)
- 一次資料：[26.04のセキュリティ変更](https://ubuntu.com/blog/ubuntu-26-04-lts-security-updates)、[LTS向け変更一覧](https://documentation.ubuntu.com/release-notes/26.04/summary-for-lts-users/)
- 一次資料：[AppArmor](https://ubuntu.com/server/docs/how-to/security/apparmor/)、[Snapの制限](https://snapcraft.io/docs/explanation/security/snap-confinement/)
- 一次資料：[UFW](https://ubuntu.com/server/docs/how-to/security/firewalls/)、[DockerとFirewall](https://docs.docker.com/engine/network/packet-filtering-firewalls/)
- 一次資料：[ライフサイクル](https://ubuntu.com/about/release-cycle)、[Proの範囲](https://ubuntu.com/pricing/pro)、[セキュリティ更新](https://documentation.ubuntu.com/security/security-updates/)
- 一次資料：[regreSSHion](https://ubuntu.com/blog/ubuntu-regresshion-security-fix)、[XZの影響範囲](https://ubuntu.com/security/CVE-2024-3094)
