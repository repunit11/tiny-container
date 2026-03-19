# 03 OCI Spec And Config

## 対象

`cmd` と `libcontainer` を接続し、親子プロセス連携のための Unix ドメインソケットとモジュール構造を整える区間です。

- `eab980d` `:adhesive_bandage: 修正`
- `0e3e349` `:package: libcontainer を追加`
- `af939cd` `:white_check_mark: 動作確認`
- `743175a` `:sparkles: Unix ドメインソケットによる通信の実装`
- `4796718` `:recycle: refactor`
- `464d0f5` `:recycle: refactor`
- `7b81a82` `:truck: ファイルをまとめてネスト`
- `4eddc8a` `:recycle: より使いやすい形にリファクタ`

## 学びなど

libcontainer: コンテナを起動・隔離・制御するための低レイヤ実装
CLIで起動して、プリントとコンテナの起動ができるようにした

### Unixドメインソケットの実装

構造体：UnixSocketServer、UnixSocketClient、UnixSocketConnection
UnixSocketServer：標準ライブラリのUnixListenerをラップ
- コンストラクタ
  - pathで受け取った場所にソケットファイルを作る
- accept
  - クライアントが接続してくるのを待つ
  - 接続を認識したらUnixSocketConnectionを作成

UnixSocketClient
- connect
  - 指定されたpathのソケットに接続
  - 接続できたらUnixSocketConnectionを作成

UnixSocketConnection：標準ライブラリのUnixStreamをラップ
- コンストラクタ
  - UnixStreamを受け取ってUnixSocketConnectionを作る
  - Mutexを使ってロックを掛ける
- send
  - 文字列を相手に送るメソッド
  - Mutexでガードしてstreamに書き込み
- receive
  - 相手から送られてきたデータを受け取る
  - ストリームをロックしてbufferで読み込む
