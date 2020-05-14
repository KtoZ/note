# PowerApps and Flow Partner AirLift Day.2

## Microsoft Flow

- Flow は Instant / Scheduled / Automated の 3 つの Trigger がある
- CDS Connector は基本的に Current Environment で OK. もう一つのほうはユーザーが自分で作るときを想定している
- Data がたくさんある場合はデフォルトで 512 Records しか取れない。最大は 100,000 Records まで変更可能
- Updates Records をしたいとき、空設定をしたい場合は blank ではなく null を設定する
- 変数宣言は最初にやること
- 複数分岐させたい場合は有料プランの Switch がおすすめ
- Scope を使うと処理をまとめて移動させたりできる
- Action の ... を選択して Error Handling を設定すると、エラー時のみの処理にしたりすることが可能
  - E.g. Teams Message Send が失敗した場合に Outlook にメールするなど
- テストは Save and Run した後に、自分でアクションを実行する必要がある
- RealTime flow も、今後追加されていく予定
- バッチの並列処理と複数処理のトランザクションは今後実装予定
- @json expression は最強
- システムユーザーを取得したい場合は Office 365 Connector を使う
- コードを見たい場合は Peek Code を使う
- Hands-on: M07*Microsoft Flow* HOL.docx

## ビジネス プロセス フロー

- List と Form を使ってどんなデバイスでも見れるようなアプリ
- Excel 連携も簡単。 Import / Export / Edit 全て簡単
- Localization も自動でしてくれる
- 新しい Unified Interface のみで作ること。昔の WebClient は使わないこと
- スマホで見せる見せないの制御もコンテンツごとに可能
- カスタムコントロールを作るときは PowerApps Control Framework と React / TS を使って作る
- 業務プロセスフローという素晴らしい機能がある
  - Stage ごとに機能を作ることができたりする
  - プロセスを定義することが大事
- ソリューションをもとにアプリを作る
- Navigation は Site Map > Area > Group > SubArea で作る

## ビジネス プロセス フローを使用したモデル駆動型アプリの構築

- Hands-on: M08_Building_Model_Driven_Apps.docx

## キャンバスアプリの埋め込み (2 オプション)

- 埋め込み方法は 4 つある
  - Web site / SharePoint / Power BI / Model Driven App
- Model Driven の Form に埋め込むのは一つだけ。複数埋め込みたい場合は iFrame を使う
- Model Driven のイベントやデータを呼び出すことが可能
- 今後 12-18 ヶ月で、キャンバスアプリと Model driven app はまとまる
- Model driven に Power BI を埋め込む場合は、 Power Plat form Admin center から設定が必要
- Hans-on: M09a - HOL Embedded Power BI.docx \*時間の都合でやらなかった
- Hans-on: M09b - HOL Embeded Canvas.docx

## ソリューションの構想

- 計画 > 設計 > 開発 > テスト > リファイン
  - 計画: ペルソナで計画
  - 設計: 全体のざっくりとした流れを作る
  - 開発: PowerApps は Agile x2 で開発するのがよい
    - ユーザーに触ってもらえるのをとにかく早くする。
    - 一週間、最長でも一ヶ月くらいの開発サイクル
    - ユーザーの声を拾って開発を進めていく
- その部署だけではなく、前後含めてビジネスフローのヒアリングが必要
  - E.g. 経理部門が使うアプリを開発するなら、前の調達部門のフローもヒアリングする
- モバイルか PC は大事。 Model driven はモバイルでたくさん入力すると大変
- OKR を測定すること
- MS でも Product Team で OKR を使っている
  - E.g. 従業員が満足である \*全体 > アプリが正常に動くこと \*部署
- Manual を見ないで直感的に使えるようにする
  - Manual をユーザーが求めている段階で UX は失敗
- AI Builder を使って開発も可能
  - 紙データを自動的に読み込んでくれたり
- 現場はデータの格納しか見ていないことが多い
  - 経営層などはデータをどう活用していくのかが大事なので、そこも考慮すること
- 一つのアプリだけでなく、たくさんのアプリをユーザーと一緒に作成していくことが大事
  - 一つの部署が成功したら、他の部署もやる、みたいな感じ
  - 長く続くような開発スタイル
