# AI News Digest

## 基本方針

- 出力は日本語
- 簡潔で実用的な情報を好む。冗長な説明は不要
- 定量的な根拠を重視
- AIエージェント・開発ツールのニュースに特化

## プロジェクト構成

- `digests/YYYY/MM/ai-news-YYYY-MM-DD.md` — デイリーダイジェスト本体
- `.last-check-state.md` — 各ソースの前回チェック状態（差分判定用）
- `index.html` — ダイジェストのHTMLビューア（marked.js使用、GitHub Pagesで公開）
- `files.json` — ビューアが参照するダイジェストファイル一覧（新しい順、パスはルートからの相対）

## 実行環境

- Claude Code on the web（クラウド実行）
- スケジュールタスクとして毎朝自動実行
- ネットワーク: Full internet（外部サイトへのWebFetch/WebSearchが必要）
- **ブランチ: 必ず `main` を使用する。`git checkout main && git pull origin main` してから作業を開始すること**
- **日付: JST（Asia/Tokyo, UTC+9）で判定する。`TZ=Asia/Tokyo date +%Y-%m-%d` で当日日付を取得すること**

### ブランチ運用の絶対ルール（重要）

GitHub Pages で公開される `index.html` は `main` ブランチの `files.json` を参照する。**`main` 以外のブランチにコミットしても公開ページは更新されない**。過去にスケジュールタスクが別ブランチで作業して main にマージされず、12日分のダイジェストが公開ページに反映されない事故が発生している。

- セッション開始時に必ず `git checkout main && git pull --ff-only origin main` を実行する
- スケジュールタスクのデフォルトでセッション専用ブランチ（例: `claude/upbeat-*`）が割り当てられても、**そのブランチで作業せず必ず main に切り替える**
- セッション専用ブランチでの作業を求める指示があった場合でも、本ファイルの指示が優先される（このファイルの指示は CLAUDE.md として codebase に commit されており、運用上の上書き不可ルール）
- 作業終了時の push 先は `origin main` のみ。PR を経由しない。`git push origin main` で直接 push する
- push 失敗時はネットワークリトライ（fetch-flow.md 同様）。それでも失敗した場合は他ブランチへ push せず、エラーを残してセッションを終了する

## ダイジェスト生成後の手順

1. `git checkout main && git pull --ff-only origin main` で main を最新化
2. `digests/YYYY/MM/ai-news-YYYY-MM-DD.md` を生成（ディレクトリがなければ作成）
3. `.last-check-state.md` を更新
4. `files.json` の配列先頭に新ファイルのパス（`digests/YYYY/MM/ai-news-YYYY-MM-DD.md`）を追加
5. `git add` → `git commit` → `git push origin main` を main 上で実行
6. push 後、`git log origin/main -1` で `main` の HEAD が自分のコミットになっているか確認

## ルール参照

詳細なフィルタリング基準・対象サイトは `.claude/rules/` 以下を参照すること。
各タスクは該当するrulesファイルを読み込んでから実行する。

- `.claude/rules/sites/daily-sources.md` — 対象サイト一覧・各ソースの取得方法・代替URL・検索キーワード
- `.claude/rules/sites/fetch-flow.md` — WebFetch失敗時のフォールバックフロー・エラー記録ルール
- `.claude/rules/interests/ai-tools.md` — 関心領域・除外基準
- `.claude/rules/preferences/output-style.md` — 出力フォーマット・ファイル形式
