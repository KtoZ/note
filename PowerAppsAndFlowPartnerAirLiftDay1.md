# PowerApps and Flow Partner AirLift Day.1

Event Page: https://www.microsoftevents.com/profile/form/index.cfm?PKformID=0x7984865abcd

Document: aka.ms/powerapps-airlift-ja

Lab import solution 1: aka.ms/powerapps-airlift-m04-ja

Lab import solution 2: aka.ms/powerapps-airlift-m12-ja

Lab import solution 3: aka.ms/powerapps-airlift-m14-ja

## PowerApps パートナーになる

- なぜ PowerApps なの？
  - 組織内の色んな場所にデータがたまっていて活用できていない
  - モバイルファーストで業務が進むようになっている
  - モバイルアプリを作成するのはコストがかかる
  - PowerApps は aPaaS \*2019 > 2022 で 3 倍の需要
  - Teams と一緒で、ものすごい勢いで成長、利用されている
  - これから Salesforce よりも成長させていく
  - 速いスピードで顧客に提供できるようになっている
  - パートナーとしては全体最適化のアプリを作っていくのがよい
- パートナーになるには
  - Embed or Empower
  - 顧客と一緒に色んなアプリを作っていくのがベスト
  - 短い期間でいろいろ作っていく
  - ユーザーの展開作業をフォローする
  - ユーザーが作れるものは作る、高度なものは開発会社が作るハイブリット
  - 1 つのアプリを作るのではなく、1000 個のアプリをユーザーと開発会社で分けて作っていく
  - ユーザーに対して導入教育をするのもよい
  - 今: Sign up
  - これから: Fulfill Requirements, Build Showcase Apps など
- 事例
  - Lotus Notes からの移行
  - 紙ベースのものを PowerApps で作る
- 開発会社が導入すると
  - ROI 40%
  - 12M\$
  - 15 ヶ月くらいでトントンになる
- 今日やるのは Level 200 の Airlift

## Power Platform の新機能

- メジャーアップデートは年 2 回 \*Feature Updates
- バグ修正やパフォーマンス改善など \*Weekly Updates
- 今まで作ってきたアプリはどうなる？
  - 発行したタイミングでスナップショットが取られて、それで動作している
  - PowerApps がアップデートしても壊れることはない
  - Weekly の恩恵を受けるためには再発行が必要
- Deploy Schedule は Region によって違う
- 開発するときに検証したい場合は別 Region を使って検証可能
- リリースのバージョンはサイトを見る
- Data > Dataflows の Analytics チェックボックスを使用すると、 Azure Data Rake にデータが格納される
- Database storage の中身
  - Database capacity / File capacity / Log capacity の 3 つになっている
  - Database capacity: Azure SQL Database
  - File capacity: Azure Blob Storage
  - Log capacity: Azure Cosmos DB
  - Capacity は Admin center から確認可能
  - 物理的な容量の上限は 4TB なのでほぼなくなる必要なし
- Region はテナントに紐付いているわけではなく Environment に紐づく
- Solution Export / Import できるようになった

## CDS データ モデリング

- 最初はコアとなる部分のエンティティを作る
- あまり正規化しすぎないようにする \*目安は 2,3 階層
- 後からの変更は簡単にできるので、作りすぎないことが大事
- 何度も作って修正してを繰り返すのが大事
- ユーザーがデータをどのように使っていくかを設計していくことが大事
- なるべく Common Data Model に寄せていったほうが良い
- Activities は Entity に対しての活動記録を取りたいときに使用する
- 利用可能範囲はユーザー、チーム、組織単位で設定可能
- トランザクションデータはユーザー、チームで制御して、 Readonly のデータは組織単位で制御するのがよい
- ロールアップエンティティは非同期でスケジュールされている。リアルタイムデータには不向き
- 計算フィールドは Calculated と Rollup がある
- Many-to-many は自動的にリレーションしてくれる
- Hierarchical Entity も設定すれば自動的に設定してくれる (e.g. 親会社、小会社、孫会社)
- cascade も細かく設定可能
- エンティティのアクセスはユーザーごとにブラックリストで作成する
- 個人が作ったエンティティはアクセス制御を設定しないと他の人は使えない
- Business Unit
  - 会社の組織単位などで作成できる
  - 営業部のユーザーがデータを作成したら、営業部の人が見れる

## グループ演習 – データモデリング

- インタビューアプリのエクササイズ: M03_Data_Modeling_Basics.docx

## CDS ソリューションの操作

- Solution を使うと Development, Test, Production をまとめることができる
- UnManaged は開発用、本番に移すときは Managed を使う
- 顧客に出すときは Managed を使う
- ソリューションチェッカーを実行するとパフォーマンス改善など全部教えてくれる
  - PowerApps の画面から有効化する必要あり
- Managed ソリューションを更新するときは Patch を使うと楽
- Hands-on: M04 - HOL Solutions.docx

## PowerApps キャンバス アプリ

- Canvas と Model-driven どっち？
  - Canvas
    - 単一なタスクを完成させたり、 Teams などに埋め込む場合はこっち
  - Model-driven
    - バックオフィス向け
    - 画面や項目が多い場合はこっち
    - Default でレスポンシブデザインになっている
    - Excel import / export 機能もある
    - 複数のリレーションがある場合はこっち
  - 組み合わせて使うのもあり (e.g. レポートを Canvas, 入力を Model-Driven)
- App Checker
  - 駄目なコードを教えてくれたり、 Accessibility と Performance も Check してくれる
- Preview and Experimental Features
  - Experimental は本番環境で使用しないこと
- Control Properties
  - IO / I / O の 3 つがある
- Variable
  - Global / Context (画面一つに対しての変数) / Collection (アプリ全体、テーブルのみ) がある
  - オフライン対応したい場合は Collection の SaveData / LoadData を使えば OK
  - データはメモリ依存なので 50MB 程度を想定している
- 取得可能な上限は 500 Rows から変更しないこと
- 委任機能を使用すればたくさんのデータをサーバーで処理できて、レスポンスを減らすことができる
  - CDS の場合は View を使う
- Aggregating Data (e.g. Sum, Max, Min) は 50000 Records まで
  - 集計フィールドを使えば OK
- OnStart は限りなく少ない状態にしたほうがよい
  - たくさんデータを処理するときは OnVisible などを使う
- Canvas app は基本的に一人しか編集できない
  - Component 単位で作るのは可能
- Hands-on: M05 Canvas Apps HOL.docx

## ビジネス ルールの実装

- モデルドリブン型専用
- 今後は Business Rules / Microsoft Flow のどっちかを使うようにする
- Business Rule でやるか JS でやるかの考えは、シンプルな場合は Business Rule でやる
- 実行順は Order of execution を参照
