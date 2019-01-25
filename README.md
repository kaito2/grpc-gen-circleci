CircleCI で python, go, typescript の gRPC コードを生成するテンプレート

## Set up

### .proto ファイル

`protos` ディレクトリに`.proto`ファイルを追加 (`helloworld.proto`は削除)

### 環境変数

以下の3つの環境変数をCircleCIのプロジェクトに設定

```
https://${GH_TOKEN}@github.com/${CIRCLE_PROJECT_USERNAME}/${CIRCLE_PROJECT_REPONAME}.git
```

`GH_TOKEN`: [Github Personal Token](https://github.com/settings/tokens) から取得

### レポジトリの初期化

```
$ git clone https://github.com/kaito2/grpc-gen-circleci.git <新規プロジェクト名>
$ cd <新規プロジェクト名>
$ git remote set-url origin <新規リポジトリURL>
$ git push -u
```

### コード生成

master に push されるたびに `generated/<LANGUAGE>` ブランチにクライアントのコードが生成される 

### ToDo

- master 以外でも コード生成ができるようにする。 (試作を試せない)