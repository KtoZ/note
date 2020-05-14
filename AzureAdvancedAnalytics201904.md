# Event: Azure による高度分析セミナー (1 日講座)

Event Page: https://www.microsoftevents.com/profile/form/index.cfm?PKformID=0x6484530abcd

Document: https://publicdoc.z13.web.core.windows.net/?prefix=AdvancedAnalytics201904/

## Section.1 バッチを中心とした分析データとトランザクションデータ

- Azure のリアルタイム情報は [Azure Heat Map](https://azureheatmap.azurewebsites.net/)
- Azure SQL Database
  - オンプレからの移行は SQL Database Managed Instance が最適
  - Stretch Database を使うとオンプレのデータを Azure に安全に移行できる
  - オンプレからの簡単な移行ツールもある (Azure Database Migration Service?)
  - Read only replica を簡単に作れる
    - JP East を R/W にして、 JP West や海外を Read only にすれば可用性が上がる
  - Auto Backup が 35 日ついているので IaaS 時代の面倒な Backup 設定はいらない
- Azure Cosmos DB
  - 応答性と可用性が高いアプリケーションを世界的な規模で構築できる
  - KVS, 列指向型, Document, Graph, (あともう一つ), の 5 種類から NoSQL を構築できる
  - Cassandra、MongoDB、Gremlin なども使える
  - vscode の extenstion から Azure 内部のデータを R/W することもできる
- Microsoft の取り組みとして MySQL などの OSS 系の DB に対して Contributing をしている

## Section.2 高速リアルタイム分析

- Azure には HDInsight Kafka と Event Hub がある
  - HDInsight Kafka
    - Apache が作ったものを Azure の PaaS に乗せている
    - IaaS に Kafka を載せてもいい。ただ Fee をあまり取っていないので HDInsight がおすすめ
    - Tool が揃っているので構築に時間をかけなくてよい
  - Event Hub
    - MS 独自のもの
    - Kafka は最小構成が高いので、軽くやるならこっちのほうが安い
    - 他の Azure Service との連携が簡単
- Azure Databricks というものある
- データをリアルタイムで Power BI に流して見たりとか色々できる

## Section.3 IoT とクラウドからのオフロード

- Azure IoT Hub がある
  - Azure IoT Edge Runtime を使って構築できる
  - SDK は Client と Server で分かれている
  - Azure IoT Edge on Ubuntu という VM の Emulator がある
  - Edge Runtime の中身は Docker と同じ。 Docker が動いていると思えばわかりやすい
- Cognitive Services という既に学習済みのサービスを入れることができる
  - IoT 側で学習させたデータをクラウドに持っていくのが今どきの考え
  - 一部の Cognitive Services は Customize もできるから、業界用語とかも学習させることができる

## Section.4 Azure Cosmos DB

- 応答性が物凄くよいので、 Azure が定めた応答性が出なかった場合は返金もしてくれる
- RDB と違って Transaction は Stored procedure で実装する
  - Partition key を揃えるなど工夫が必要
- オンライン学習サービスがある。 Cosmos DB 以外もある。日本語もある
  - Sandbox を使うので無料
  - [Azure Cosmos DB の NoSQL データを扱うラーニング パス - Learn | Microsoft Docs](https://docs.microsoft.com/ja-jp/learn/paths/work-with-nosql-data-in-azure-cosmos-db/)
  - [Azure Cosmos DB Workshop - Workshop Powerpoint Deck](https://cosmosdb.github.io/labs/)
- 各社の事例を検索できる (Cosmos DB 以外もたくさんある)
  - [Microsoft Customers Search](https://customers.microsoft.com/en-us/search?sq=&ff=&p=0&so=story_publish_date%20desc)
