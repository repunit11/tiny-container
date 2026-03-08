# 03 OCI Spec And Config

## 対象

- OCI Runtime Spec の読み込み
- `config.json` の扱い
- 設定値のバリデーション方針

## 学びなど

- container構造体、state構造体を作成
- stateの構造体はOCI Specに由来している
- stateの構造体の仕様: https://github.com/opencontainers/runtime-spec/blob/main/runtime.md
- containerの構造体はおそらくファイルとかの保存場所を持っておきたいからだと思う
- #[]はRustのattribute記法で、コードに追加情報を与えたり、マクロとして動いたりするもの
- Ubuntuのイメージをpullするスクリプトを作成した
- runc specを実行することでイメージを実行するための手順書を作成する
- これはOCI bundleが完成した状態である
