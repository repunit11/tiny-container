# 01 Setup And Workspace

## 対象

プロジェクトを単一バイナリから workspace 構成へ広げ、CLI の入口を作るまでの区間です。

- `97b5182` `:tada: initial commit`
- `6d3f460` `:gear: workspace を使うように`
- `606baec` `:sparkles: workspace を追加`
- `1b0b0e7` `:gear: LICENSE を追加`
- `60b6cf2` `:truck: clap を導入`
- `1c8b68e` `:sparkles: サブコマンドを扱えるように`
- `656b7c9` `:recycle: refactor`

## 学びなど

- `cargo new`でプロジェクトを新規作成できる
- `cargo init`で今いるプロジェクトをrustプロジェクトにできる
- Cargo.toml は変更してもいいが、Cargo.lock は変更しない。cargoが変更してくれる
- workspaceとは、1つのプロジェクトを複数のクレートという単位に分割して運用するための仕組み（参考：[https://doc.rust-lang.org/book/ch14-03-cargo-workspaces.html]）
- Cargo.toml にworkspaceを利用することと、そのメンバーを明示する
- workspaceのメンバーにあるパッケージを作る方法： `cargo new {package} --lib`
- 今回のプロジェクトはほかの人の学習用OSSを模写するだけなのでLICENCEは元のものをそのまま貼っている
