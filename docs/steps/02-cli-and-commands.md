# 02 CLI And Commands

## 対象

- `clap` を使った引数処理
- サブコマンド (`run`, `exec` など) の導線
- CLI層と実行ロジック層の分離

## 学びなど

- clapとは、Command Line Argument Parser for Rustの略であり、RustでCLIを作るときに利用する定番のクレートである
- 導入方法は、 `cargo add clap --features derive (-p cmd)`

ここでCLI全体のメタ設定を行う

```rust
#[clap(
    name = "tiny-youki",
    about = "tiny-youki (WIP) - Open Container Initiative runtime",
    author = "n4mlz",
    arg_required_else_help = true
)]
```

ここでサブコマンドの引数の型の定義を行う。  
コマンドの実装は別の部分で行う。

```rust
enum SubCommands {
    #[clap(name = "create", about = "create a container")]
    Create {
        container_id: String,

        #[clap(short = 'b', long, value_name = "PATH", required = true)]
        bundle: PathBuf,
    },
}
```
