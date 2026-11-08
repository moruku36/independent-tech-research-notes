**日本語** | [English](2026-npaka-windows-security-layers.md)

# Windowsの標準セキュリティ：機能の適用条件とエージェントの権限

- npakaによるWindows 11のセキュリティ解説記事。起動、カーネル、アプリ、保存データ、通信の標準機能を整理する。
- Defender、SmartScreen、Smart App Control、UAC、BitLocker、VBSなどは役割と適用条件が異なり、搭載だけで一律の保護を意味しない。
- OS間の防御率比較ではない。一般的なデスクトップアプリの権限と、ログイン後の情報流出を別途考える必要がある。

## 実務向けの読み解き（7行）

- Secure BootやTPM、VBSによるシステム保護と、ユーザーファイルのアクセス制御を分けて考える。
- SmartScreenの警告、Smart App Controlの実行制御、Defenderの検出を同じ機能として扱わない。
- UACの管理者昇格確認がなくても、通常ユーザーの権限で読める情報はある。
- プライバシー設定だけですべてのWin32デスクトップアプリを制限できるとは考えない。
- BitLockerやWindows Helloは重要だが、実行中のアプリやセッションの悪用を包括的に防ぐものではない。
- AIエージェントの作業コピー・認証情報・外向き通信を別々に管理する設計を検討する。
- 機能の有効状態と対象アプリを読み取り専用で棚卸しする案であり、本ノートでは設定変更・攻撃実験を行っていない。

## 書誌・確認状況

- 指定記事：Windowsのセキュリティの仕組み - 標準機能と安全に使うための対策
- 著者：npaka。公開：2026-11-08 11:26（記事表示、JST）。
- 種別：個人の解説記事。学術論文・比較ベンチマークではない。DOI／arXiv IDなし。
- 確認日：2026-11-08 JST。対象は閲覧時点のWeb本文で、固定版番号はない。
- 状態：指定記事の本文を末尾まで確認。Microsoft公式資料でデスクトップアプリの権限、UAC、Smart App Control、VBS／メモリ整合性、BitLocker、Firewallを選択的に照合。
- 未実施：実機の構成・有効状態の確認、マルウェア実行、防御率測定。全攻撃事例の原報告は個別検証していない。

## 問い・方法・比較条件

Windows 11の標準機能が、どの攻撃段階とデータを保護し、どこに追加の注意が必要かを示す入門記事。機能、攻撃事例、設定確認の観点を並べ、Macとの定性的な対応にも触れる。OS版・ハードウェア・アプリ・管理ポリシーを揃えた比較試験はない。

本ノートではMicrosoft公式資料で主要な適用範囲を補足する。エージェントへの提案は、記事内の実験結果ではない。

## 主張と根拠

| 層 | 記事が扱う機能 | 読み取りの範囲 |
|---|---|---|
| 起動・カーネル | Secure Boot、Trusted Boot、TPM、VBS／HVCI | 起動の検証、鍵・測定値の保護、分離された環境でのカーネルコード整合性を区別 |
| アプリ | Defender Antivirus、SmartScreen、Smart App Control | 検出・評判確認・実行制御は別の機能。有効状態と条件を確認する |
| 権限・データ | UAC、アプリ権限、BitLocker、Windows Hello、パスキー | 昇格、アクセス、保存時の暗号化、認証を分ける |
| 通信 | Windows Firewall、TLS／HTTPS、Wi-Fi／VPN | 通信の許否と通信路の暗号化は別の制御 |

Microsoftの公式説明では、従来型デスクトップアプリにはプライバシー設定の例外がある。Microsoft Storeから取得したという理由だけでも、すべて同じSandboxや権限制御が適用されるとは言えない。UACは管理者権限の利用を制御するが、標準ユーザーの権限でアクセス可能なデータの隔離を自動で作るわけではない。

Smart App Controlは安全性の判断と署名を利用する実行制御で、評価モード／強制モードを区別する。VBS／メモリ整合性にはハードウェアやドライバーの条件がある。端末のWindows版、設定、組織ポリシーを見ずに、すべて有効と断定しない。

BitLockerの主な対象は紛失・盗難などに伴う保存データの露出。デバイスの暗号化と通常のBitLocker管理では利用条件が異なる。Windows Firewallは受信・送信の両方を制御できるが、公式の既定動作には送信許可があるため、存在だけで情報持ち出しの阻止を保証しない。

記事のLumma、ClickFix、3CXは、情報窃取、操作の誘導、配布経路の侵害を説明する事例として読む。発生規模や全期間の検出実績は、この読書作業では独立に確認していない。

## 限界・比較時の注意

記事の強弱評価には統一された攻撃セット、成功率、試行回数がない。「WindowsよりMacが安全」などの一般的な優劣へ拡張しない。特にアプリモデル、エディション、管理設定、更新状態で条件が変わる。

保護機能が有効でも、ユーザーやエージェントが許可された範囲で秘密を読む・送る問題は残る。HTTPSやVPNは通信路を保護するが、接続先の正当性やアプリの意図まで保証しない。

## 関連ノートと応用案

- [Ubuntuの標準セキュリティ](2026-npaka-ubuntu-security-layers.ja.md)：Desktop／Server、AppArmor・Snap、コンテナ通信の適用条件を補う。
- [Macの標準セキュリティ](2026-npaka-macos-security-layers.ja.md)：機能が守る対象と適用範囲を対応付ける対の記事。
- [Trojan Horse：リポジトリ汚染攻撃](../agent-safety/2026-trojanforge-repository-poisoning.ja.md)：OSの保護とは別に、エージェントが外部の命令を取り込む経路を考える材料。

本ノートの応用案は、エージェント用作業領域、通常ユーザーの私的ファイル、Git・API認証、通信先を分けて棚卸しすること。管理者として起動しないことだけで、ユーザーデータの隔離が完了したとは判定しない。

## 無料でできる確認案（未実施）

OS版・エディションと、Windowsセキュリティ画面の保護状態、暗号化状態、Firewallのプロファイルを読み取り専用で記録する。利用するエージェントが一般的なデスクトップアプリか、別の隔離環境を使うかを確認し、実行ユーザーがアクセスできる作業範囲と照合する。

回復キー・認証情報・私的ファイルを報告へ転記しない。設定の切替、再起動、ドライバー変更、未知のプログラム実行はこの確認に含めない。

- 活用状態：提案のみ。実機確認・実装採用なし。
- 次の確認：対象アプリの隔離方式、実際の保護状態、送信ルール、作業領域と秘密情報の境界。

## 出典

- 指定解説記事：[npaka](https://note.com/npaka/n/n45fc13b66f85)
- 一次資料：[デスクトップアプリとプライバシー](https://support.microsoft.com/en-gb/windows/privacy/windows-desktop-apps-and-privacy?nochrome=true)、[ファイルシステムアクセスの例外](https://support.microsoft.com/en-us/windows/privacy/windows-file-system-access-and-privacy)、[UAC](https://learn.microsoft.com/en-us/windows/security/application-security/application-control/user-account-control/)
- 一次資料：[Smart App Control](https://learn.microsoft.com/windows/apps/develop/smart-app-control/overview)、[メモリ整合性](https://learn.microsoft.com/en-us/windows/security/hardware-security/enable-virtualization-based-protection-of-code-integrity)
- 一次資料：[BitLocker](https://learn.microsoft.com/en-us/windows/security/operating-system-security/data-protection/bitlocker/)、[Firewallの既定動作](https://learn.microsoft.com/en-gb/windows/client-management/mdm/firewall-csp)
