# AI News Digest

AIエージェント・開発ツールのニュースを毎朝自動収集し、日本語ダイジェストとして配信するシステム。

## 仕組み

- Claude Code on the web のスケジュールタスクで毎朝 7:00 (JST) に実行
- 対象サイトから WebFetch / WebSearch で情報を収集し、前回との差分を抽出
- Markdown形式のダイジェストを生成し、GitHub Pagesで公開

## ビューア

https://rfdnxbro.github.io/ai-news/

## Forkして使う場合

### Public vs Private リポジトリ

| 項目 | Public | Private |
|---|---|---|
| GitHub Pages | 無料で利用可能 | GitHub Pro以上が必要 |
| スケジュールタスク | 動作する | 動作する |
| ダイジェスト内容 | 誰でも閲覧可能 | リポジトリメンバーのみ |

### セットアップ手順

1. このリポジトリをFork
2. GitHub Pages を有効化（Settings > Pages > Source: main, / (root)）
3. Claude Code on the web でスケジュールタスクを作成（`CLAUDE.md` の手順に従う）
4. `files.json` を `[]` に、`.last-check-state.md` を初期状態にリセット

### セキュリティ上の注意

- **GitHub Pages は常にPublic公開**: Private リポジトリでも Pages は外部からアクセス可能。ダイジェスト内容に社内情報や個人情報を含めたい場合は Pages を無効化すること
- **スケジュールタスクの権限**: Claude Code のスケジュールタスクはリポジトリへの push 権限を持つ。信頼できるアカウントでのみ設定すること
- **`.claude/rules/` の内容**: 監視対象サイトやフィルタリング基準が含まれる。組織固有の関心領域を追加する場合、Private リポジトリの利用を推奨
