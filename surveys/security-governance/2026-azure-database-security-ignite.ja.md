**日本語** | [English](2026-azure-database-security-ignite.md)

# Ignite 2026のAzureデータベースセキュリティ更新

## 概要

- **何についてのものか** Azure SQL Database、Azure Database for PostgreSQL Flexible Server、Azure HorizonDBのセキュリティ更新をまとめたMicrosoftの公式記事。
- **何を述べているか** 暗号化、ID管理、マスキング、ネットワークに関する9項目のうち、6項目を一般提供、3項目をパブリックプレビューと発表した。
- **留意点** 発表の提供段階を記録した。利用条件、リージョン、移行時の影響は製品と構成によって異なる。

## 実務向け6行

- Azure SQL Databaseは、透過的データ暗号化（TDE）を保護するAES-256の顧客管理キーと、正規表現による動的データマスキングが一般提供。
- Azure SQLのTDEスキャンの一時停止・再開と、データベース単位のマネージドIDはパブリックプレビュー。
- PostgreSQL Flexible ServerはVNet統合からプライベートエンドポイント対応構成に変更できる。変更は元に戻せず、接続の中断を伴う。
- Azure HorizonDBはPrivate Link、Microsoft Entra認証、ユーザー割り当てマネージドIDが一般提供。
- HorizonDBの顧客管理キーによる保存時暗号化はパブリックプレビュー。Microsoft Learnでは、地理冗長バックアップとの併用に制約がある。
- 応用案。導入前に、鍵の管理主体、IDへの権限付与、DNSと接続経路、復旧要件をワークロードごとに整理する。

## 書誌・確認範囲

Pieter Vanhove、Microsoft Azure SQL Blog、2026年11月25日公開。2026年11月26日（JST）に発表本文とMicrosoftの補足資料を確認した。表は発表時点の提供段階を示す。実環境での挙動は未検証。

| サービス | 更新 | 発表時点の提供段階 |
| --- | --- | --- |
| Azure SQL Database | AES-256の顧客管理TDEプロテクター | 一般提供 |
| Azure SQL Database | TDEスキャンの一時停止・再開 | パブリックプレビュー |
| Azure SQL Database | 正規表現による動的データマスキング | 一般提供 |
| Azure SQL Database | データベース単位のマネージドID | パブリックプレビュー |
| Azure Database for PostgreSQL Flexible Server | VNet統合からプライベートエンドポイント対応構成への変更 | 一般提供 |
| Azure HorizonDB | Azure Private Link | 一般提供 |
| Azure HorizonDB | 顧客管理キーによる保存時暗号化 | パブリックプレビュー |
| Azure HorizonDB | Microsoft Entra認証 | 一般提供 |
| Azure HorizonDB | ユーザー割り当てマネージドID | 一般提供 |

## 根拠と限界

- **暗号化とマスキング。** TDEプロテクターはデータベース暗号化キーを保護する。Microsoft LearnはAzure SQL DatabaseのAES-256プロテクターの保管先としてAzure Key Vault PremiumまたはManaged HSMを挙げる。正規表現によるマスキングは権限の限られた利用者への検索結果を加工し、保存値は維持する。特権利用者やUNMASK権限を付与された利用者は元の値を参照できる。
- **IDの役割。** Entra認証はデータベースへ接続する主体に関わる。マネージドIDは、データベースの処理が別の対応Azureリソースへ資格情報の手動管理なしで接続するために使える。接続先での権限付与は必要で、Azure SQLのプレビュー資料ではストレージへのアクセスを例にしている。
- **ネットワークと復旧。** PostgreSQLのガイドによると、既存サーバーのネットワーク変更は不可逆で、実行中は既存接続が閉じられる。変更後は接続経路を構成するまでアクセスできない。切り替え計画にはプライベートDNS、利用側の接続、レプリケーションの確認を含める。HorizonDBのドキュメントは、顧客管理キーと地理冗長バックアップは併用できないとしている。
- **証拠の範囲。** Microsoftによる機能と提供段階の説明で、独立した可用性・性能の測定は掲載されていない。

## 応用・無料の確認案

提案・未試行。1つのデータベースを題材に、鍵と管理主体、マスキングと閲覧権限、名前解決、プライベート接続、復旧目標を表にして公式資料と照合する。検証環境があれば架空データを使い、想定したIDで接続と参照ができることを確かめる。本番移行の判断前に、隔離した環境で再接続と復元を評価する。

## 関連ノート

- [Ignite 2026のAzure基盤発表](../articles/2026-azure-ignite-platform-announcements.ja.md)
- [マルチクラウドのセキュリティ設計](2026-multi-cloud-security-architecture.ja.md)

## 出典

- [Microsoft Azure SQL Blogの発表](https://techcommunity.microsoft.com/blog/azuresqlblog/whats-new-in-azure-database-security-stronger-encryption-simpler-identity-and-ne/4575935)
- [顧客管理キーを用いたTDE](https://learn.microsoft.com/en-us/azure/azure-sql/database/transparent-data-encryption-byok-overview?view=azuresql)
- [TDEスキャンの一時停止と再開](https://techcommunity.microsoft.com/blog/azuresqlblog/take-control-of-transparent-data-encryption-scans-suspend-and-resume-now-in-prev/4571096)
- [正規表現による動的データマスキング](https://learn.microsoft.com/en-us/azure/azure-sql/database/dynamic-data-masking-regex?view=azuresql)
- [ストレージ接続用のデータベース単位のID](https://techcommunity.microsoft.com/blog/azuresqlblog/give-each-azure-sql-database-its-own-identity-for-storage-access-preview/4575974)
- [PostgreSQLのネットワーク変更](https://learn.microsoft.com/en-us/azure/postgresql/network/how-to-migrate-vnet-private-endpoint-capable-server)
- [HorizonDBの機能と制約](https://learn.microsoft.com/en-us/azure/horizondb/overview/overview)

[分野別索引](README.ja.md) | [読書一覧](../../docs/reading-list.ja.md)
