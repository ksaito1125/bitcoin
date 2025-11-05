# 開発コンテナ

Bitcoinをビルドできる開発コンテナです。

## 要件

``doc/build-unix.md``にビルドに必要な要件が記載されています。

## ファイル構成

開発コンテナのファイル構成は下記の通りです。

```
tree .devcontainer/
.devcontainer/
├── devcontainer.json
├── Dockerfile
└── README.md

1 directory, 3 files
```

``Dockerfile``にビルドに必要なコンテナと追加設定が定義されています。

GitHub Codespaceとdockerデーモンの両方で動作します。

## ビルド手順

```
cmake -B build
```

```
cd build
make
```

以上