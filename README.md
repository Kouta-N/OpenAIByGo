https://qiita.com/kbys-fumi/items/f60dd965a6d022b8d33a

# Go の学習用環境

こちらのリポジトリは Go の学習用環境です。最小限の構成にしてあるので、何か追加する際はご自身で適宜修正してください。

## スタートガイド

※ 事前に Docker Desktop for Mac や Docker Desktop for Windows などでご自身の PC 環境に Docker のインストールは済ませておいてください

はじめにリポジトリをクローンして、対象のディレクトリに移動します

```
$ git clone https://github.com/fumiakikobayashi/go-learning-environment.git
$ cd go-learning-environment
```

下記コマンドを実行してコンテナを立ち上げてください。（`make`コマンドを使用することで、`Makefile`に定義しているコマンドを実行することができます。）

※ このコマンドは初回のみ実行します

```
$ make build
$ make up
```

続いて`make ps` コマンドを実行し、コンテナが`runnning`になっていることを確認してください

```
$ make ps
NAME                            COMMAND             SERVICE             STATUS              PORTS
go-learning-environment-app-1   "/bin/sh"           app                 running

```

これで環境の構築は完了です。最後に実際に golang を実行できるかどうか確認します。

下記コマンドを実行して、コンテナに入ります。

```
$ make app
```

`go run main.go`で`main.go`を実行します。下記のように現在時刻が表示されれば成功です。

```
$ go run main.go
Welcome to the playground!
The time is 2023-01-23 12:20:52.048513751 +0000 UTC m=+0.000050001
```

## Tips

- 各種コマンドは Makefile をご覧ください [Makefile](https://github.com/PicoCELA/onpremis-api/blob/main/Makefile)
