# Web API The Good Parts

## 1 章 - Web API とは何か

- さまざまな API を集めて公開している API ディレクトリサービスがある
  - [ProgrammableWeb - APIs, Mashups and the Web as Platform](https://www.programmableweb.com/)
- API で公開すべきものは、コアで価値のある部分
- LSUDs (public) と SSKDs (private) で API の美しさの定義を変える

## 2 章 - エンドポイントの設計とリクエストの形式

- 短くわかりやすい URI を作る
  - NG: http://api.example.com/service/api/search
  - OK: http://api.example.com/search
- むやみに省略形の言葉は使わない
- URI は基本的に全て小文字にする
- ユーザーの友達一覧取得の URI はこんな感じで、途中に ID が出てきてもよい
  - http://api.example.com/v1/users/:id/friends
- リソースへアクセスするための URI は複数形にする
- 取得数と取得位置は limit / offset がよい
- ページング多い場合は相対位置ではなく、絶対位置を使用してデータを取得する
  - 例えばこの ID より前のものや、この時刻より古いもの、など
- GET の検索キーワードが一つの場合は `q` を使用することが多い
- 自分自身のエイリアスを作る場合は `me` がよい
- HATEOAS の概念を取り入れて、次に進めるようなリンクを返してあげるものよい

## 3 章 - レスポンスデータの設計

- JSONP は必要なときだけサポートする
- 配列はそのまま返さずに、オブジェクトで包んでから返すようにする
- データはできればフラットのほうがよいけど、階層構造のほうがわかりやすいときはそっちでもよい
- 次のページがある場合は `hasNext` など使用してあるかないかを返してあげる
- 大きな数値を返す場合は、文字列化した数値も返してあげる
- エラーを返すときはメッセージとコードを返す

## 4 章 - HTTP の仕様を最大限利用する

- Status code 409: リソース競合のエラー。既に登録済みだった場合など
- Status code 410: リソースが存在しないエラー。既に削除済みだった場合など
- プロキシサーバーはレスポンスをキャッシュする場合がある
- HTTP には Expiration Model と Validation Model の 2 つのキャッシュが存在する
- Expiration Model
  - 期限が切れたら再度アクセスする
  - Expires: 更新すべき日時がわかっている場合に使用
  - Cache-Control: 定期更新でないものや、更新頻度が低くないけどサーバーのアクセス頻度を下げてほしいときに使用
- Validation Model
  - サーバーに更新が必要がどうか問い合わせる
  - 更新が不要な場合は `304` を返す
  - サーバー側が `Last-Modified` と `ETag` を見て、ハッシュなどと照らし合わせてどうするか判定する
- キャッシュさせたくないときは `Cache-Control: no-cache` にする
- Vary と Accept-Language を使用して、言語ごとにキャッシュを設定できる
- メディアタイプを自分で作る場合はこんな感じにする
  - `application/vnd.{companyname}.{yourformat}`
- Request の Accept は複数指定できて、 `q=0.9` など優先順位を決められる
- public にアクセス可能な API の Response は CORS に対応するため `Access-Control-Allow-Origin: *` にする
- 認証情報も渡す場合は `Access-Control-Allow-Credentials: true` にする

## 5 章 - 設計変更をしやすい Web API を作る

- 常に最新版を返すエイリアスはいらない
- サポートは利用規約に記載する
- LSUDs を自分たちで使う場合はオーケストレーション層を作ると使いやすい

## 6 章 - 堅牢な Web.API を作る

- ブラウザから直接アクセスされることがない場合は `X-Requested-With: XMLHttpRequest` をつけると XSS XSRF JSON ハイジャックされなくなる
- パラメーターを改ざんして -100 などを送られた場合、バグるのを防ぐにはきちんと入力チェックするようにする
- リクエストの再送信も簡単なため、再送信しても動作しないように整合性をチェックする
- Set-Cookie は secure にすることが可能
- 大量アクセスを防ぐためにはレートリミットを実装する
- レートリミット時は 429 と Retry-After を返すようにする
- X-RateLimit-Limit X-RateLimit-Remaining X-RateLimit-Reset などを常に返すようにするのもよい
