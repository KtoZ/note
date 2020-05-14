# Microsoft Teams Development Bootcamp Day 1

Event Page: https://www.microsoftevents.com/profile/form/index.cfm?PKformID=0x7760266abcd

Document: https://shtakedat3-my.sharepoint.com/personal/tarom_shtakedat3_work/_layouts/15/onedrive.aspx?id=%2Fpersonal%2Ftarom%5Fshtakedat3%5Fwork%2FDocuments%2F201909%5FTeams%5FDev%5FBootcamp

## 00 Microsoft Strategy and Bootcamp Objectives

- Teams はモダンワークプレイス戦略の一つ (Teams / Security / Cloud Shift)
- MS はパートナーの製品をアプリ化したい
- Co-Sell とは、パートナーが作ったものを MS が営業して売ってくれる仕組み
- MS 営業向けカタログに載せるイメージ
- クラウドイネーブルデスクに加入すればビジネスアイデアから開発まで相談可能

## 01 Partner Opportunity to develop on Microsoft Teams

- MS をツールとして使って製品を作って欲しい by サティア
- MS 主体で 500 名以下の企業に対して Skype をやめて Teams に移行するようにした (10 月 -> 7 月末で約 50%)
- Outlook などを Teams に移行する動きがある
- Teams 中でも特にメリットがよいのは Office 365 と連携しているからセキュリティが高いこと
- MS が作って欲しいものとしてはインダストリソリューションが一番高い
- インダストリソリューションは MS が手を出さないので協業できる
- 機能特化アプリだと MS が取り込んでしまうかも
- Azure の機能を使ったものなどを開発すると MS の教科書に載る
- Azure AD
  - 使用しているユーザーが多いので、それを組み合わせたアプリ開発がおすすめ
  - Office 365 を使っていると裏で意識せずに動いている
  - セキュリティ製品として購入する企業も多い
- Graph API を使えば全てのリソースに同じようにアクセス可能
- 文化の違いでアメリカだとエンドユーザーが直接アプリを入れて使うことが多いから、マーケットに出すと見て貰えることも多い
- Azure AD を組み合わせたアプリ開発にすると Azure AD のマーケットにも表示される

## 02 Microsoft Teams Architecture Overview

- 月 1,2 回程度、クライアントのアップデートがあるくらい開発が活発
- いろいろなマイクロサービスや Azure, Office 365 プラットフォームと連携して作成されている
- ディザスタリカバリもついているからどこかで障害が起きても動く
- JP だけでもデータ保存場所に East and West がある
- ファイルは Sharepoint 以外のクラウドストレージに保存することも可能

## 03 Overview of Teams Dev Platform

- Tab
  - Configurable Tabs と Static Tabs がある
  - Tab をどこで使用するかどうかは app manifest で指定する
- Bot
  - MS Bot Framework が必ず必要
  - 既に Bot がいればそのまま使える
  - SDK を使用するために C# か Node.js を使ったほうが良い
  - v3 は .NET Framework ベース。 v4 は .NET Core ベースなので互換性がない
  - 開発するときは v4.5 を使ったほうが良い
  - teams / personal / groupChat の 3 つの Bot がある。メンション付きで呼び出すなど動きが少し違う
- Bot and Tab を組み合わせて作るのがベストプラクティス
- Azure AD のシングルサインオンを作うのがよい
  - Co-Sell するには Azure AD のシングルサインオンが必要
- Messaging Extension
  - 三点リーダーから呼び出せる
  - 中身は Bot なので Bot Extension を使って作る
- Connector
  - 外部アプリケーションのアクションを通知してくれるもの
  - Card で通知することも可能。 URL や Button もつけることができる
- Task Module
  - モーダルポップアップ機能
  - ディープリンクという Teams の機能を呼び出すものも作れる
  - ディープリンクを作る場合は Javascript SDK を使って作らないとブラウザに飛んでしまう
- Activity Feed
  - 画面左上の通知アイコンを使う機能

## 04 Design Guidance - Best Practices to Design Great Microsoft Teams Apps

- 資料を一通り読んでほしい。ガイドラインなどが書いてある
- MS のプラットフォーム上に作る場合は、プラットフォームを知ってから作って欲しい
- 知らない状態で作ってしまうと MS のアップデートによって使えなくなってしまうなどの自体が起きたりする

## 05 Overview of Teams Graph APIs for administration

- Graph API
  - MS 製品の様々な収集、操作を Graph API で行っている
  - 昔は Outlook API / Sharepoint API など分かれていた。現在は Graph API にまとまった
  - bata にしかない Channel や Chat のリストを取得したい場合は待たないとダメ。 v1 になってから作って欲しい
  - graph API の変更内容は英語版で見ること
  - me リソースがある
  - 使用するには Graph App ID が必要。 Teams App ID とは別
  - ID は Azure Portal のアプリの登録または Graph quick start から取得できる
  - Teams API のアクセス許可は Read.All または ReadWrite.All がある
  - チームの作成を Graph とテンプレートを組み合わせて作ることが可能
  - 機密データにアクセスする保護された API へのアクセスは承認が必要
    - 要求フォームにアクセスして MS に承認依頼する
  - ユーザー権限または Application 権限で Teams にアクセス可能
- Teams
  - チームの作成はテンプレートからも可能
  - チームを削除した場合は 30 日間のみ復元可能
  - チームをアーカイブして読み取り専用にすることも可能

## 06 Overview of Teams Graph APIs for app scenarios

- Graph を組み合わせないとメッセージの取得などはできない
- アプリのインストールを Graph を使ってできる = ユーザー全員に Bot をインストールすることができる
- Bot は @メンションのメッセージのみ取れる
- 音声系の Bot も作れる
- ダイヤルパットの 1 とか 5 とか押して反応するやつもできる
- Bot から必要な人を呼び出して会議させるようなものも作れる (Call and API)
- Voice 系の v1 は早くて年明け
- Tab は開くたびにリロードがかかる。何度もログインする面倒くささを防ぐために SSO を使用する
- Bot の Azure AD SSO を使用する場合は ID から入力する必要がある

## 07 Package and Publish Teams apps

- ストアは多言語対応していない
- 審査の都合上、日本語を使用する場合は localizationInfo を設定する必要あり
- mpnId は必ず入れること。会社の識別 ID になる。 Co-Sell に必要
- manifest 変更時は必ず新しいバージョンにすること
- Privacy policy と Term of service は必須
- 展開方法は Teams Store またはテナントアプリ の 2 つある

## 08 Manage Teams Apps

- アメリカだと社内にエンジニアがいてカスタムアプリを作って配布している
- Teams center から管理ポリシーの設定が可能
- 怪しい場所から拾ってきたアプリを入れられたら困るから、アプリの管理ポリシーは正しく設定すべき
- 全社員に使ってもらいたいものを左側のアイコンとしてピンどめすることが可能

## 09 Teams IP Co-Sell Opportunity

- Modern Workplace ISV パートナー:追加要件なしで Co-Sell になれる
- アプリケーション開発者として登録する必要あり
- アプリケーションポリシーは専用のページじゃないとダメ。企業のポリシーではダメ
- 検証用とユーザーのアカウントを作らないとダメ。ないと専用チームがアプリの確認ができない
- サインアウトも作らないとダメ
- 審査はかなり厳しい。早くても 2 ヶ月くらいかかる

## Note

- ストアの課金モデルは今の所ない。月額サービスとかにするしかない
- アプリのアップデートは自動的に行われるのか、手動なのか (ストア、テナントともに)
  - 自動で行われる。マニフェストを変えないアップデートならそもそもアップデートをする必要がない
- ストアのアップデートするときは毎回長い審査が必要なのか
  - 一度審査が通っているのでそれなりに早いと思うが、必要だと思う
