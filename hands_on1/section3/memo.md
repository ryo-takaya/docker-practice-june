## Dockerファイルとは？
  Dockerのイメージ(コンテナの元になるもの)を作成する際のコマンドをコード化して、一つのファイルにまとめたもの。
  Dockerファイルを使わないと手動でコマンドを打たなくては行けない

## Dockerファイルを使う場合

### Dockerファイルからイメージを作成

  ```docker build```

### Dockerイメージからコンテナを作る

  ```docker run```

docker build(dockerファイルからイメージを作成) -> docker run(dokcerイメージからコンテナを作成)

## Dockerファイルのコマンド達

### FROM

  FROMで指定したDockerイメージをベースに、これから記述するコマンドを実施する

### RUN
  
  FROMで指定したイメージに対してコマンドを実行する

### COPY
  
  docker buildして出来上がるDockerイメージにコピーしたいファイルを指定する

### ADD
  COPYコマンドとほぼ同じですが、以下の2点が異なります。

URLの指定が可能である
tarアーカイブでgzip、bzip2、xzで圧縮されていた場合、自動で展開される
例えば、hoge.txtをgzipで圧縮し、tarアーカイブしたhoge.tar.gzファイルは、イメージ上では展開されます。つまり、/tmp/hoge.txtという形でコピーされます。

### CMD 

docker runコマンドで実行する際のコマンドを指定します。
docker run時に上書き可能

### ENTRYPOINT

docker runコマンドで実行する際のコマンドを指定します。

### ENV

docker buildでイメージを作成する際に指定する環境変数を定義することができます。

### EXPOSE

Dockerコンテナ内で公開するポートを指定します。