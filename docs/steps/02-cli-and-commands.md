# 02 CLI And Commands

## 対象

- `clap` を使った引数処理
- サブコマンド (`run`, `exec` など) の導線
- CLI層と実行ロジック層の分離

## 学びなど

- clapとは、Command Line Argument Parser for Rustの略であり、RustでCLIを作るときに利用する定番のクレートである
- 導入方法は、 `cargo add clap --features derive (-p cmd)`
