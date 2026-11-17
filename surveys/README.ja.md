# サーベイノート

[English](README.md) | **日本語**

論文・技術記事・登壇資料の読書ノートです。テーマ別の一覧から、資料ごとのノートへ進めます。

[最近の追加](../docs/reading-history.ja.md) · [全読書・活用一覧](../docs/reading-list.ja.md) · [リポジトリの概要](../README.ja.md)

## テーマ一覧

### AIエージェント・ソフトウェア開発

| テーマ | 主な内容 |
| --- | --- |
| [コーディングエージェント・開発](coding-agents/README.ja.md) | コード生成、レビュー、自動修復、検証 |
| [人とAIの協働](human-ai-collaboration/README.ja.md) | 職場でのAI活用、学習、注意、目標の共有 |
| [AIエージェントの安全性](agent-safety/README.ja.md) | 権限、攻撃、ミスアラインメント、報酬ハッキング |
| [おとり・欺瞞とLLM防御](deception-defense/README.ja.md) | おとりや偽の情報を用いた防御 |

### インフラ・運用・セキュリティ

| テーマ | 主な内容 |
| --- | --- |
| [LLM推論基盤](llm-infrastructure/README.ja.md) | 推論環境、メモリー、キャッシュ、コスト、オーケストレーション |
| [クラウドの耐障害性・SRE](cloud-resilience/README.ja.md) | 障害注入、復旧、クラウド、DevOps |
| [セキュリティ・ガバナンス](security-governance/README.ja.md) | 個人情報、認証情報、組織統制、クラウドセキュリティ |

### モデル・技術動向・経済

| テーマ | 主な内容 |
| --- | --- |
| [生成モデル・3D環境](generative-modeling/README.ja.md) | 生成、編集、データセット、評価 |
| [予測・ベンチマーク](forecasting/README.ja.md) | 時系列予測、データセット、不確実性 |
| [イベント・技術記事・仕事／労働研究](articles/README.ja.md) | 製品発表、技術報告、イベント、仕事に関する研究 |

関連する別コレクション：[経済・企業開示](../economics/README.ja.md)は `surveys/` の外に整理しています。

## 研究メモの原則

- 実験を行っていない場合は「再現済み」と記載しない。
- 論文のシミュレーション結果を、実運用の攻撃成功と混同しない。
- 引用文献の一次URLと確認状態を必ず残す。
- すべてのノートに日本語版（`*.ja.md`）を用意する。
- すべてのノートの冒頭（タイトル直後）に、3行の**概要**（何についてのものか／何を述べているか／留意点）を置く。

学術論文・プレプリント、研究記事、実務家の報告、企業資料は種別を区別します。各資料の項目は、テーマ別一覧と全読書一覧から参照できます。

## ファイルの置き場所

| パス | 内容 |
| --- | --- |
| `surveys/<テーマ>/<年>-<スラッグ>.md` | 英語のノート |
| `surveys/<テーマ>/<年>-<スラッグ>.ja.md` | 対応する日本語版 |
| `surveys/<テーマ>/README.md` / `README.ja.md` | テーマ内のノート一覧 |
| [docs/](../docs/reading-list.ja.md) | 分野を横断する読書一覧、研究計画、確認票 |

[ノートのテンプレート](template.ja.md)に沿って、一次URL・確認状況・要約・限界・活用案を残します。

[リポジトリREADME](../README.ja.md) · [読書履歴](../docs/reading-history.ja.md) · [全読書一覧](../docs/reading-list.ja.md)
