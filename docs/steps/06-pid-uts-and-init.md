# 06 Rootfs And Mounts

## 対象

PID namespace、UTS namespace、init プロセスを導入し、コンテナのライフサイクル管理を形にしていく区間です。

- `e0725c2` `:zap: pid namespace を分離`
- `58bf18a` `:sparkles: namespaces 関連のメソッドを分離`
- `a95e324` `:recycle: 分離した namespaces の実装を使うように`
- `9744e0d` `:sparkles: init プロセスの処理を追加`
- `4059bd1` `:zap: state.json を書き換えるメソッドを追加`
- `6c77122` `:zap: state.json を適切に書き換えるように変更`
- `344075e` `:adhesive_bandage: エラー文を修正`
- `12cb1d6` `:recycle: namespaces.rs を別モジュールに分離`
- `bfebc3a` `:sparkles: uts を追加`
- `ef307be` `:package: libc を追加`
- `1d7c792` `:sparkles: uts の設定を実装`

## 今日やったこと

- 

## 理解したこと

- 

## 次に確認すること

- 

