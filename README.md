# gh-wf

カレントリポジトリの `.github/workflows/` を **fzf で検索・プレビュー**する gh 拡張。

GitHub Actions の Web UI は「削除済みだが run 履歴が残っているワークフロー」を一覧に残し続けるうえ、ワークフローの検索・絞り込みが弱い。`gh-wf` はデータソースを **ローカルの現存 yaml** にすることでこの 2 つを解決する。

- 削除済みワークフローは物理的に存在しないので自動的に除外される
- fzf でインクリメンタル検索しながら、右ペインに yaml の中身をプレビュー

## 必要なもの

- [`fzf`](https://github.com/junegunn/fzf)
- [`gh`](https://cli.github.com/)
- [`bat`](https://github.com/sharkdp/bat)（無くても `cat` にフォールバック）

## インストール

```bash
gh extension install /Users/ut61z/src/github.com/ut61z/claude-code/gh-wf
```

## 使い方

```bash
gh wf          # Enter = そのワークフローの run 一覧
gh wf --web    # Enter = ブラウザでそのワークフローを開く
```

### fzf 内のキーバインド

| キー | 動作 |
|------|------|
| `Enter` | 起動オプションに応じて run 一覧 or ブラウザ |
| `Ctrl-O` | ブラウザでワークフローを開く |
| `Ctrl-R` | run 一覧を表示 |
| `Ctrl-E` | `$EDITOR` で yaml を開く |
| `Ctrl-Y` | ファイル名をクリップボードにコピー |
