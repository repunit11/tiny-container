# tiny-container

コンテナランタイムの仕組みを理解するために、参考実装を1コミットずつ追って学習するリポジトリです。
実運用向けではなく、学習・検証目的のコードです。

## 概要

- Rustで最小構成のコンテナ実装を学ぶ
- [OCI Runtime Specification](https://github.com/opencontainers/runtime-spec) の必要最低限な部分に準拠

## このリポジトリについて

このリポジトリは学習目的で以下のプロジェクトを模写しています。

- Reference: https://github.com/n4mlz/tiny-youki
- Original Author: `n4mlz`

最終的に参考元とほぼ同一のコードになる可能性があります。
差分がある場合は、学習メモ・検証コード・実験的変更です。

## 使い方

```bash
cargo build
cargo test
```

必要に応じて各クレートを個別に実行してください。

## 免責

このコードは学習目的で提供しており、動作保証はありません。
利用により生じたいかなる損害についても責任を負いません。

## License

MIT License
- Original: Copyright (c) 2025 n4mlz
- See [LICENCE](./LICENCE)
