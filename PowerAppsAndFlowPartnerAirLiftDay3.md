# PowerApps and Flow Partner AirLift Day.3

## PowerApps の展開 & セキュリティとガバナンスの構築

- よくある手順は Dev / Test / Product の順で展開
- 今は別環境に持っていくと全て設定し直さなければならない
- 今後は環境変数が用意されて、それを展開できるようになる
- Azure AD Group で Security roles が可能
- Azure DevOps と連携して ALM を管理することも可能
- PowerApps Builds Tools を使うと色々自動化可能
- COE Toolkit があるから使うならダウンロードしてね
  - https://aka.ms/COEStarterKit
- DLP Policy Editor を使うと Business と None-Business でセキュリティ違反しているものを見たりできる
- ユーザーにアプリを作らせないことは不可能
  - ただし、作ったものをすぐ削除するようなことは可能
  - ある企業の例だと、サンドボックスを用意して特定の期間で作れば許可するみたいなフローにした
- Hands-on: M12-ALM HOL.docx

## カスタム API とコネクタの構築 & フレームワークを使用した再利用可能なコンポーネントとコントロールの構築

- 自分で作ることも可能だし、Swagger の読み込みか Postman Collection から作成可能
- コネクションを我々が作って、顧客が使うように提供することも可能
- オンプレゲートウェイを使うと、オンプレ環境の API も操作可能
- Hand-on: M13a - HOL Connect to Custom APIs.docx \*時間がなくてやらなかった
- Hand-on: M13b - HOL Reusable Components.docx

## PowerApps AI Builder

- コンセプトは AI を全てのアプリに、全ての人に
- モデルになるデータは CDS に格納されている
- 4 つの AI がある
  - Prediction / Form Processing / Object Detection / Text Classification / Business Card Reader​
- Prediction
  - 1H 程度で実装可能
  - 二項分類予測。 (e.g. 過去の履歴をもとに、晴れるか、晴れないか)
- Form Processing
  - 1H 程度で実装可能
  - 請求書など 15 枚のサンプルがあれば作成可能
  - 日本語対応まだしていない
- Object Detection
  - 写真をタグ付けすれば、それかどうかの判定が可能
  - 棚卸しのアプリなどで使えそう
- Text Classification
  - Tweet など会話系の内容をタグ付けしてくれる
  - これも日本語まだ
  - 担当者の適切な割当などができる
- Business Card Reader​
  - モデル学習不要
  - これも日本語まだ
  - ほとんどの名刺の内容を取ってくれる
- Hand-on: M14aObjectDetection.docx
- Hand-on: M14bForm Processing.docx \*時間がなくてやらなかった
- Hand-on: M14cBusiness card reader.docx \*時間がなくてやらなかった

## PowerApps Portals

- 顧客とやりとりをするために Azure AD を使わなくて良いようにするため MS が作った
- PowerApps を外部向けのサイトとして公開できる
- 最初から多言語対応もしている
- キャンバスアプリや Model Driven アプリと同じようにサイトが作れる
- 特定のユーザーだけ見せたいとか CDS と同じような制御が可能
- Power BI の埋め込むも可能
- 行政のサイトも作った例もある
  - https://memo.tyoshida.me/powerapps/possibility-using-powerapps-for-government/

## まとめ、振り返り、Q&A

- ユーザーと開発者はどの Office を契約したらよい？
  - per app plan / per user plan / Seeded PowerApps の 3 つがある。プランによって金額が異なる
  - ユーザー: per app plan / per user plan のどっちかがよい
  - 開発会社: コンピテンシーがあればいらない。コンピテンシーはなんでもよい
  - Seeded PowerApps だと CDS が使えないから微妙
  - PowerApps Portals のライセンスはまた別
- AI Builder はいつから日本で使える？
  - 全くわからない
