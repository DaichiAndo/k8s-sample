# k8s-sample

Kubernetesを用いたサンプルアプリケーションです。
Kubernetes上でExpressで作成したAPIを動作させます。
APIはデータベース（MySQL）と通信を行います。

## 全体構成

APIとデータベースそれぞれのNamespace（`app` と `db`）を作成しています。

データベース側ではDeploymentでデータベースコンテナのPodを管理し、
ServiceでPodへのアクセスを受け付けます。

API側も同様にDeploymentでAPIコンテナのPodを管理し、
ServiceでPodへのアクセスを受け付けます。
これに加えて、API側では、データベース情報を管理するためにConfigMapとSecretを使用しています。

## APIコンテナイメージ

APIコンテナは以下のイメージを使用しています。
このイメージは、Node.jsのExpressで作成されたAPIを実行します。

https://hub.docker.com/r/kdldando/express-api-sample

また、このイメージのソースコードは以下です。

https://github.com/DaichiAndo/express-api-sample
