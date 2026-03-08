# 01 Setup And Workspace

## 対象

- プロジェクト初期化
- Cargo workspace 構成
- `cmd` / `libcontainer` のクレート分割
- LICENSEの追加

## 学びなど

- `cargo new`でプロジェクトを新規作成できる
- `cargo init`で今いるプロジェクトをrustプロジェクトにできる
- Cargo.toml は変更してもいいが、Cargo.lock は変更しない。cargoが変更してくれる
- workspaceとは、1つのプロジェクトを複数のクレートという単位に分割して運用するための仕組み（参考：[https://doc.rust-lang.org/book/ch14-03-cargo-workspaces.html]）
- Cargo.toml にworkspaceを利用することと、そのメンバーを明示する
- workspaceのメンバーにあるパッケージを作る方法： `cargo new {package} --lib`
- 今回のプロジェクトはほかの人の学習用OSSを模写するだけなのでLICENCEは元のものをそのまま貼っている
