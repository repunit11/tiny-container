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

- container構造体、state構造体を作成
- stateの構造体はOCI Specに由来している
- stateの構造体の仕様: https://github.com/opencontainers/runtime-spec/blob/main/runtime.md
- containerの構造体はおそらくファイルとかの保存場所を持っておきたいからだと思う
- #[]はRustのattribute記法で、コードに追加情報を与えたり、マクロとして動いたりするもの
- Ubuntuのイメージをpullするスクリプトを作成した
- runc specを実行することでイメージを実行するための手順書を作成する
- これはOCI bundleが完成した状態である
- serde_jsonを追加した。これは、rustのデータ構造とJSONのデータ構造を変換するために利用するライブラリ
- serialize: rustの構造体⇒JSON出力
- deserialize: JSON⇒rustの構造体
- impl: structで構造体のフィールドを定義する、implでメソッドの処理を実装する
