# homebrew-tap

[rikukadev](https://github.com/rikukadev) のツールを Homebrew で入れるための tap。

```bash
brew install rikukadev/tap/kagerou
```

| formula | 何か |
|---|---|
| [kagerou](https://github.com/rikukadev/kagerou) | PR や E2E で使い捨てるプレビュー環境を、今あるコンテナ定義から作る |

## 更新のしかた

**`Formula/` は手で編集しない。** 各リポジトリの goreleaser が、リリースのたびに
ここへ formula を push する。バージョンを上げたいときは、上流のリリースを出す。

## 入れ方の使い分け(kagerou)

| 入れ方 | 向いている場面 |
|---|---|
| `brew install rikukadev/tap/kagerou` | 手元で常用する |
| `npx kagerou diagnose` | まず 1 回試す(インストールしない) |
| `go install github.com/rikukadev/kagerou/cmd/kagerou@latest` | Go の環境がある |
