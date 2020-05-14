たぶんみんな同じようなものが多いと思いますが、何か参考になるものがあるかもしれないのでよかったら見ていってください。

## 開発環境

### Visual Studio

[Visual Studio 2019 IDE - Programming Software for Windows](https://visualstudio.microsoft.com/vs/)

- 最強の IDE. ほぼ全ての開発はこれ。
- Version ごとに共存可能なので、職場ではプロジェクトによって変えている。
- 家では何も気にせず最新版の 2019.
- Project に対しての Git の操作も殆どこれ。
- Plugin はこんな感じ。元々が最強だからあまり多く入れていない。リンクを張っておく。
  - [ReSharper - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=JetBrains.ReSharper)
    - Visual Studio がイケてない時代から使っている。有料。
    - とりあえず Alt + Enter を押せば大体いい感じにしてくれる。
    - たしか 30 Days は Free なので、使ってみて価格分の価値を見出だせたら購入するのがよいかも。
  - [Power Commands for Visual Studio - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.PowerCommandsforVisualStudio)
    - Format document on save と Remove and Sort Usings on save くらいしか使っていない。
    - 100% ではないけど、この 2 つがあれば大体 Style guide は保てる。イケてない Prettier みたいなイメージ。

### Visual Studio Code

[Visual Studio Code - Code Editing. Redefined](https://code.visualstudio.com/?wt.mc_id=DX_841432)

- 最強の Editor. 最強なのに軽い。 Visual Studio で作る Solution 以外は全部これ。
- Qiita の記事とか Markdown を書くときも使っている。
- Front-end の開発もこれ。
- Git も殆どこれ。
- Linux Server への SSH 接続とか Docker 接続もこれ。
- たぶん一番触っている時間が長い。
- 最近は Visual Studio XXXX で Google 検索すると、こっちが出てくるくらいみんな使っている。
  - Visual Studio が検索しづらいので、正直に言うと名前を変えてほしい。
- C# と同じく、死ぬまでに一度は Contribute したい。
  - どうすればよいかよい案を持っている人いたら教えて下さい。がんばります。
- Plugin が結構インストールしているからいくつかオススメをピックアップする。殆ど有名なやつかも。
  - [Code Spell Checker - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker)
    - Spell が怪しいやつに波線をつけてくれる。日本語はチェックしてくれない。
    - 余談だが Qiita という Word にも波線がつく。
  - [EditorConfig for VS Code - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)
    - EditorConfig という有名な設定ファイルを動かすやつ。
    - タブのインデントや最終行の改行、空白のトリミングなどをしてくれる。
  - [GitLens — Git supercharged - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens)
    - Git を見やすくしてくれる。ファイルの履歴や行の履歴などもすぐ出せる。
    - とりあえず入れておいたほうがよい。
  - [Live Server - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
    - 右下のアイコンをクリックするだけでローカルサーバーが立ち上がる。
    - 素の HTML とか JS を書いているときに、ブラウザで見たいときに使う。
  - [Live Share - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare)
    - リモート先の相手の画面を見ながら一緒にコーディングできる、たぶん。
    - Screen share をしながらペアプロをするときに使う、予定。
    - 開発フレンドがいないので使ったことはない。
  - [Paste JSON as Code - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=quicktype.quicktype)
    - JSON を色んな言語の Schema に変換してくれる。
    - TypeScript で開発しているときに一度だけ使った。
  - [Prettier - Code formatter - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
    - Prettier という有名なコードキレイキレイツールを動かすやつ。
    - 一番よく使う Plugin. というより、保存時に勝手に動くようにしている。
    - Markdown も Format してくれて、一番よいのが日本語と英単語の間にスペースを入れてくれるところ。
    - キチンと言語ごとに設定しないと、既存のソースコードをキレイキレイして Git Diff がやばいことになるから気をつけて。
  - [Remote Development - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)
    - Linux に接続したりするのに使っている。
    - Remote SSH, Containers など全部入りのやつ。
  - [Settings Sync - Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync)
    - Visual Studio Code の設定ファイルを GitHub Gist で管理できて、複数端末で設定を同期できる。
    - Windows と Mac を使っている僕でも正しく使えている。

### IntelliJ IDEA

[IntelliJ IDEA：JetBrains によるプロ開発者向け Java IDE](https://www.jetbrains.com/ja-jp/idea/)

- 職場から Java や PHP を強いられたときに使っている。これも最強だけど C# では使わない。

### DataGrip

[DataGrip：データベースおよび SQL 用の JetBrains 製クロスプラットフォーム IDE](https://www.jetbrains.com/ja-jp/datagrip/)

- Database 管理用アプリケーション。 IntelliJ についてきたから使っている。
- 色んな種類の Database に接続できるから便利。

### Management Studio

[SQL Server Management Studio (SSMS) のダウンロード - SQL Server Management Studio (SSMS) | Microsoft Docs](https://docs.microsoft.com/ja-jp/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)

- SQL Server を Monitoring したいときとか、管理系の特別なことをしたいときに使っている。

### Git Bash

[Git for Windows](https://gitforwindows.org/)

- Windows はコマンドプロンプトが死んでいるので、これがないと生きていけない。
- Power shell がいらないときの CLI は殆どこれ。

### Postman

[Postman | The Collaboration Platform for API Development](https://www.getpostman.com/)

- API Request に使っている。コレクション管理も出来るから便利。
- 最近、 [Postman で API Document を作る - Qiita](https://qiita.com/KoKeCross/items/e1cb7bea5551101c711f) という記事も書きました。

### Sourcetree

[Sourcetree | Free Git GUI for Mac and Windows](https://www.sourcetreeapp.com/)

- Git History が見やすいので使っている。 Commit などは Visual Studio を使っているので、ほぼ History を見る専門。

### Adobe XD

[Adobe XD 体験版ダウンロード | UI/UX デザインと共同作業ツール](https://www.adobe.com/jp/products/xd.html)

- 画面デザインやワイヤーフレームを作るときに使っている。色々出来て今どきっぽくてイケてて便利。
- 共同作業などをしなければ Free で使える。

### draw.io

[draw.io](https://www.draw.io/)

- 構成図を描くときに使っている。アイコンもたくさんあるし、線も繋げやすい。
- 今まで紹介してきたやつと違い、ブラウザで動く。

### Excel

リンクなし。

- 職場からこの形式で設計書を強いられたときに使っている。日々、 Git の Conflict や、罫線や文字色などと戦っている。
- 一年前くらいに、 [設計書は Excel だけじゃなくて Markdown も使ってほしい - Qiita](https://qiita.com/KoKeCross/items/2e233219f73ffbe7d674) という記事を書いくらい、苦手なアプリケーション。
