# homebrew-tap

[rikukadev](https://github.com/rikukadev) のツールを Homebrew で入れるための tap。

```bash
brew install rikukadev/tap/kagerou
brew install rikukadev/tap/sashiki
```

| formula | 何か |
|---|---|
| [kagerou](https://github.com/rikukadev/kagerou) | PR や E2E で使い捨てるプレビュー環境を、今あるコンテナ定義から作る |
| [sashiki](https://github.com/rikukadev/sashiki) | copy-on-write で使い捨ての DB ブランチを作る(MySQL / PostgreSQL) |

## 更新のしかた

**`Casks/` は手で編集しない。** 各リポジトリの goreleaser が、リリースのたびに
ここへ formula を push する。バージョンを上げたいときは、上流のリリースを出す。

## 入れ方の使い分け(kagerou)

| 入れ方 | 向いている場面 |
|---|---|
| `brew install rikukadev/tap/kagerou` | 手元で常用する |
| `npx kagerou diagnose` | まず 1 回試す(インストールしない) |
| `go install github.com/rikukadev/kagerou/cmd/kagerou@latest` | Go の環境がある |

## 上流のリリースに要るもの

各リポジトリに **`HOMEBREW_TAP_GITHUB_TOKEN`**(このリポジトリへの Contents: write を持つ
fine-grained PAT)を登録する。名前は両リポジトリで揃えてあるので、PAT は 1 つでよい。
未登録の間は cask の push だけがスキップされ、リリース自体は通る。

## sashiki の常駐について

macOS ネイティブの常駐(launchd)は `sashiki init --platform darwin` が行うので、
`brew services` は使わない。cask の caveats にも同じことを書いてある。
