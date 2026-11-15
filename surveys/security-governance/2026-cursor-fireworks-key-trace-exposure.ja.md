**日本語** | [English](2026-cursor-fireworks-key-trace-exposure.md)

# Cursor侵害：委託先キー・エージェント記録・拡張配信

## 概要

- **何についてのものか** 委託先に置いたキーと、過去のエージェント記録の流出に関する事件報道。
- **何を述べているか** Cursorは、コピーされた記録内の認証情報から侵害が広がり、拡張配信キャッシュに不正な拡張が置かれたと説明する。
- **留意点** 報道本文は取得できず、以下は提供者の一次発表に基づく。独立したフォレンジック調査ではない。

## 実務向けの読み解き（6行）

- Cursorによると、Fireworksに発行したキーから読み取り専用の共有バケットが流出した。
- Privacy Modeを使わない過去の記録の一部に、未マスクの認証情報があった。
- その認証情報から、一部の社内SaaSとデータへアクセスされた。
- 後に盗まれた認証情報で、Cursorの拡張配信キャッシュが改ざんされた。
- 約11時間で最大5,000人が不正ビルドを受け取った可能性があり、感染確認人数ではない。
- 応用案は、共有記録の保存を絞り、秘密情報を除去し、学習データへの権限と配信権限を分離すること。

## 書誌・確認範囲

The Hacker News、2026-11-15。カテゴリの検索結果で見出しと冒頭を確認し、直接・モバイルの本文取得は失敗。2026-11-15 JSTにCursor Team『An update on our recent security incident』（2026-11-13）と、2026-11-09更新のFireworks告知の主要部分を確認。マルウェア実行・独立調査は未実施。

## 証拠・限界

Cursorは10月29日に改ざんされたAnthropic.claude-code 2.1.312・2.1.313が配信されたと説明し、Open VSXは非影響とする。公式アプリ・更新系とPrivacy Modeの入力・コードは今回の流出範囲外という説明も、封じ込め状態とともに提供元の主張として扱う。Fireworksは限定したアカウント群への広い影響を説明するが、その告知だけでは該当するCursor発行キーを独立に特定できない。両事件の接続はCursorの説明に依拠する。

## 関連資料

- [承認と秘密情報流出](2026-apiiro-agent-approval-secret-leaks.ja.md)
- [KVキャッシュの露出](2026-cloudflare-kv-cache-exposure.ja.md)

## 無料の確認計画・活用状態

提案・未実施。架空の認証情報だけで、記録取得、秘密情報の除去、保存共有、後段SaaS、成果物配信のデータフローを無料で図式化する。読み取り専用のデータに再利用できる権限が含まれないか、短期・対象限定の権限でどこを断てるかを確認する。保存期間、管理者、失効経路を記録する。次は提供者の通知と独立証拠を確認してから個別対応を決める。実キーの走査・更新や拡張の導入は行っていない。

## 出典

- [依頼された報道URL](https://thehackernews.com/2026/11/stolen-fireworks-ai-key-led-to-cursor.html)
- [報道のカテゴリ冒頭抜粋](https://thehackernews.com/search/label/Supply%20Chain/)
- [Cursor事件報告](https://cursor.com/blog/security-incident-update)
- [Fireworks告知](https://fireworks.ai/security/bulletins/october-2026-security-incident-update)

[テーマ索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
