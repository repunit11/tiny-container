# 02 CLI And Commands

## 対象

`libcontainer` の最小構成を用意し、`Container` と `State` を定義して `state.json` を保存できるようにする区間です。

- `e40e566` `:package: パッケージを追加`
- `151e471` `:sparkles: container と state の定義`
- `fa328d7` `:sparkles: Ubuntu のイメージを pull するスクリプトを追加`
- `80658c6` `:gear: bundle を ignore`
- `fc0f32d` `:package: serde_json を追加`
- `81c1a15` `:sparkles: 定数の定義`
- `35c9876` `:zap: state の実装`
- `c86d518` `:sparkles: container の実装`

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

- serde, oci-specのライブラリを追加
- serde: シリアライズ/デシリアライズ用のライブラリ
- oci-spec: OCI仕様を扱うライブラリ
