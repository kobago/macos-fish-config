# macOS Fish Config

macOS 向けの fish 設定です。[CachyOS の fish 設定](https://github.com/CachyOS/cachyos-fish-config) をもとに、Linux 専用の設定を取り除き、macOS で動くように直しています。

## 必要なツール

`macos.fish` は次のツールを前提にしています。[Homebrew](https://brew.sh) でインストールしてください。

```fish
brew install fish eza bat
```

| ツール | 使っている場所 |
| --- | --- |
| [fish](https://fishshell.com) | シェル本体 |
| [eza](https://github.com/eza-community/eza) | `ls` / `la` / `ll` / `lt` / `l.` のエイリアス |
| [bat](https://github.com/sharkdp/bat) | `MANPAGER` (man ページの色付け表示) |
| [Homebrew](https://brew.sh) | `update` エイリアス (`brew update && brew upgrade`) |

eza のエイリアスは `--icons=always` を付けているため、アイコンを表示するには [Nerd Font](https://www.nerdfonts.com) をターミナルのフォントに設定してください。

```fish
brew install --cask font-hack-nerd-font
```

## プラグイン (任意)

[fisher](https://github.com/jorgebucaran/fisher) で次のプラグインを入れて使っています。`macos.fish` 自体はこれらがなくても動きます。

```fish
fisher install pure-fish/pure jorgebucaran/autopair.fish franciscolourenco/done
```

| プラグイン | 内容 |
| --- | --- |
| [pure-fish/pure](https://github.com/pure-fish/pure) | プロンプト |
| [jorgebucaran/autopair.fish](https://github.com/jorgebucaran/autopair.fish) | 括弧・引用符の自動補完 |
| [franciscolourenco/done](https://github.com/franciscolourenco/done) | 時間のかかるコマンドの終了を通知 |

done の通知条件は、次のコマンドで一度だけ設定します (ユニバーサル変数なので保存されます)。

```fish
set -U __done_min_cmd_duration 10000
set -U __done_notification_urgency_level low
```

## インストール

`macos.fish` を fish の `conf.d` に置くと、起動時に自動で読み込まれます。

```fish
cp macos.fish ~/.config/fish/conf.d/
```
