**日本語** | [English](2026-anthropic-skills-over-mcp-tasks.md)

# ClaudeのMCP更新：スキル配布・バックグラウンド処理・途中確認

## 概要

- **何についてのものか**：ClaudeとClaude CodeでのSkills over MCP、Tasks、Elicitation、File UploadsについてのAnthropicの発表。
- **何を述べているか**：MCPサーバーは手順の配布、長時間処理、途中での入力確認を扱える。ファイル転送は今後の展開として発表した。
- **留意点**：機能とプラン、管理者の設定で提供状況が異なる。拡張を使うには両側の対応も必要。

## 実務向け6行

- Skills over MCPでは、接続先がツールと一緒に手順を配布し、Claudeが必要なときに読み込む。
- 公開ベータでPro・Max・Ultraは既定で有効。Teamは管理者が有効にでき、Enterpriseは今後対応予定。
- Tasksはサーバーのバックグラウンド処理、Elicitationは処理中に利用者へ入力を求める機能。
- TasksとElicitationはPro・Max・Ultraで一般提供され、Team・Enterpriseへ順次展開中。
- File Uploadsは今後展開予定。モデルの文脈にファイルを入れずに送れるが、送信先のサービスにはファイルが渡る。
- 応用案は、接続先ごとに対応機能、同意の表示、許可操作、進行状態、ファイルの送信先を点検すること。

## 書誌・確認範囲

Anthropic、2026年11月24日。2026年11月25日（JST）に公式発表とMCP拡張の関連資料を確認。プランや提供状況は発表時点。接続、処理、ファイル転送の試用は未実施。

## 根拠と限界

- **提供段階。** Skills over MCPは公開ベータ。TasksとElicitationの展開状況は別。File UploadsはPro・Max・Ultraと一部のTeam・Enterpriseで今後提供予定とされる。利用にはクライアントとサーバーの両方が該当機能に対応する必要がある。
- **信頼と権限。** MCP Skillsのベータ仕様は、サーバー提供のスキル本文を信頼できない入力として扱う。ファイルのハッシュは承認対象と取得内容を照合する手がかりで、提供元や手順の信頼性までは証明できない。スキルの承認とツールの認可は個別に扱い、影響の大きい操作には利用者の承認を残す。
- **非同期処理とファイル。** Tasksはバックグラウンド処理の状態や結果の取得を定める。Elicitationの例では処理中に利用者の入力を受ける。ファイル転送では、文脈に入るかどうかに加え、送信先と保存方針を確認する。

## 応用・無料の確認案

提案。読み取り専用の架空コネクタとダミーファイルを用意し、手順の出所、再承認が必要な変更、処理中の状態、操作や送信の前に利用者へ確認する箇所を記録する。

## 関連ノート

- [型付きのエージェント機能](2026-skillware-typed-agent-capabilities.ja.md)
- [MCPの対策分担](../security-governance/2026-mcp-security-three-tier-mitigation.ja.md)

## 出典

- [指定の日本語発表](https://claude.com/ja/resources/articles/skills-over-mcp-tasks-and-more)
- [英語の発表](https://claude.com/resources/articles/skills-over-mcp-tasks-and-more)
- [MCP Skills拡張仕様](https://skills.extensions.modelcontextprotocol.io/specification/beta/skills)
- [MCP Tasks拡張仕様](https://tasks.extensions.modelcontextprotocol.io/specification/2026-07-28/tasks)
- [MCP File Uploadsの提案](https://blog.modelcontextprotocol.io/posts/exploring-file-uploads-and-downloads-in-mcp/)

[分野別索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
