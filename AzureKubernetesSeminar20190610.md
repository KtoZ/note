# Event: 開発者のための Kubernetes ～ Azure で学ぶコンセプトと実践～

Event Page: [開発者のための Kubernetes ～ Azure で学ぶコンセプトと実践～](https://www.microsoftevents.com/profile/form/index.cfm?PKformID=0x6880072abcd)

Document: [decode2019_PPT_Template](https://seminarshare.blob.core.windows.net/20190610k8s/k8s4dev01_basic.pdf) / [Azure コンテナ関連サービスと DevOps2](https://seminarshare.blob.core.windows.net/20190610k8s/k8s4dev02_devops.pdf)

## しくみがわかる Azure Kubernetes Service

- Docker を分散環境で動作させるのが難しい。そのために Kubernetes が誕生した
- Google では殆ど Kubernetes で動いている
- 仮想分散環境の (ほぼ) デファクトスタンダード
- 自前で Kubernetes を作るとめんどくさい。 AKS を使うとすごく楽
- 分散システムデザインパターンは Kubernetes の作者が書いた
- ReadinessProbe は Ready 用のヘルスチェック
- Health check は yml で書く。いくつかパターンがあるのでアプリにあったものを設定する
- コンテナが使用する CPU／メモリの設定は必ず設定すること
  - Resource Limits / Resource Requests
- Kubernetes のスケジュールアルゴリズム
  - [community/scheduler_algorithm.md at master · kubernetes/community · GitHub](https://github.com/kubernetes/community/blob/master/contributors/devel/sig-scheduling/scheduler_algorithm.md)
- Polling がずっと動いていて、何かが起こったときに検知して動く
- ReplicaSet のオートヒーリングは Pod が再起動するのではなく新しい Pod を作る
- vscode の Kubernetes Extension を使うと GUI で Pod が確認できる
  - Delete もできる
- ReplicaSet ではなく Deployment で書くほうがよい
- 水平スケールは向いているけど、垂直スケールは向いていない
- Event Trigger で Pod を動かす新しいオープンソースの KEDA がある
- RedHat のサポートが一番よいのは Azure (Microsoft の本社に RedHat Team がある)
- Kubernetes がいらない場合
  - 月 1 deploy だったり、オートスケールもいらないシステム
  - 一人しか Kubernetes が使えないとかだと凄く茨の道

## Azure コンテナ関連サービスと DevOps / Azure Kubernetes Service 利用パターン

- Container は最近のトレンド
- Cloud Native と組み合わせるのに自動化があるといい
- 疎結合システム/マイクロサービス構築のベストプラクティス集
  - [The Twelve-Factor App （日本語訳）](https://12factor.net/ja/)
- Azure でどれを選択して App を作る？
  - [Azure コンピューティング サービスのデシジョン ツリー - Azure Application Architecture Guide | Microsoft Docs](https://docs.microsoft.com/ja-jp/azure/architecture/guide/technology-choices/compute-decision-tree)
- Azure Container Registry が Docker Hub より優れている理由
  - Azure 内にあるから近いからレイテンシーがいい
  - Private にできる (Docker Hub はお金がかかる？)
- 効果を聞かれたときに答えるのに有効な書籍: Lean と DevOps の科学
- DevOps は開発者が必要なものを開発者が決めて使うのがよい
- Canaria release の参考サイト (Azure Pipeline)
  - [Controlling Deployments using Release Gates | Azure DevOps Hands-on-Labs](https://www.azuredevopslabs.com/labs/vstsextend/releasegates/)
- モノリシックをマイクロサービスにするときは MS に相談してくれれば対応する

## Note

- 次回とか: [2019/04/25 初めての Kubernetes 体感ツアー · GitHub](https://gist.github.com/hoisjp/80eecf000983d731a0b5be4cd0b2bbaa)
