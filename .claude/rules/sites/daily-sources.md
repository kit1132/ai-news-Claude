# デイリーチェック対象サイト

## 取得方法の凡例

- **RSS**: RSS/Atom フィードを取得し、XMLから新着エントリを抽出する
- **WebFetch**: HTMLページを直接取得する
- **WebSearch**: 検索エンジン経由で情報を取得する

各ソースの「取得方法」は優先順序を示す。フォールバック条件（403/429時の挙動、リトライ手順など）の詳細は `fetch-flow.md` を参照。

RSS URLの記載がないソースはRSS未提供。WebFetch が常時403を返すソースは、取得方法の記載順にかかわらずWebSearchが実質的なプライマリ手段となる。

---

## 最優先

### Claude Code Changelog
- URL（優先）: https://code.claude.com/docs/en/changelog
- URL（フォールバック）: https://github.com/anthropics/claude-code/blob/main/CHANGELOG.md
- 取得方法: WebFetch
- 注目点: 新バージョンリリース、破壊的変更、新機能
- 頻度: 毎日確認
- 備考: WebFetch安定。GitHub版は大きいため429になることがある

### Anthropic Blog / News
- URL: https://www.anthropic.com/news
- 検索キーワード（WebSearch用）: `Anthropic news announcement 2026`
- 取得方法: WebFetch → WebSearch
- 注目点: 新モデル、新プロダクト、API変更、料金変更
- 頻度: 毎日確認

### Claude Release Notes（サポートサイト）
- URL: https://support.claude.com/en/articles/12138966-release-notes
- 検索キーワード（WebSearch用）: `Claude release notes update 2026`
- 取得方法: WebFetch → WebSearch
- 注目点: Claudeプロダクト全体のリリースノート（Web/Desktop/Mobile/API含む）。Changelogとは別軸の情報源
- 頻度: 毎日確認

### OpenAI Blog / News
- URL: https://openai.com/news
- RSS URL（優先）: https://openai.com/news/rss.xml
- 検索キーワード（WebSearch用）: `OpenAI announcement release 2026`
- 取得方法: RSS → WebSearch
- フィード本文: 要約のみ（タイトル・説明・URL）。詳細が必要な場合は記事URLをWebFetchで追加取得
- 注目点: 新モデル発表（GPT-5等）、DevDay、ポリシー変更、大型機能発表、パートナーシップ
- 頻度: 毎日確認
- 備考: 公式RSSフィード復活済み（2025年9月）。2024年時点でpubDateの順序不正確の報告あり、現在も該当するかは要確認

### OpenAI Platform Changelog
- URL: https://platform.openai.com/docs/changelog
- 検索キーワード（WebSearch用）: `OpenAI platform changelog API update 2026`
- 取得方法: WebFetch → WebSearch
- 注目点: モデルリリース・廃止予定、API仕様変更、料金変更、新エンドポイント追加、SDK更新
- 頻度: 毎日確認

### ChatGPT Release Notes
- URL: https://help.openai.com/en/articles/6825453-chatgpt-release-notes
- 検索キーワード（WebSearch用）: `ChatGPT release notes new features 2026`
- 取得方法: WebFetch → WebSearch
- 注目点: ChatGPTの新機能（Canvas、Deep Research、Memory、Voice Mode等）、UI変更、プラン別機能開放（Plus/Pro/Team/Enterprise）、モバイル対応
- 頻度: 毎日確認

### Google Workspace Updates Blog
- URL: https://workspaceupdates.googleblog.com/
- RSS URL（優先）: https://feeds.feedburner.com/GoogleAppsUpdates
- 取得方法: RSS → WebFetch → WebSearch
- フィード本文: 全文あり（Blogger/FeedBurner経由のAtomフィード）
- 注目点: Gemini for Workspaceの新機能、Docs/Sheets/Slides/Gmail/Meet統合、管理者向け変更
- 頻度: 毎日確認
- 備考: FeedBurnerフィード安定稼働（2026-04-01更新確認済み）。リンクURLがFeedBurnerプロキシ経由になる場合がある

### Google Gemini App Release Notes
- URL: https://support.google.com/gemini/answer/13594961
- 検索キーワード（WebSearch用）: `Gemini app release notes update 2026`
- 取得方法: WebFetch → WebSearch
- 注目点: Geminiアプリの機能追加・変更、モデル切替、プラン別機能差分
- 頻度: 毎日確認

### Google The Keyword（AI カテゴリ）
- URL: https://blog.google/technology/ai/
- RSS URL（優先）: https://blog.google/technology/ai/rss
- 検索キーワード（WebSearch用）: `Google AI announcement Gemini 2026`
- 取得方法: RSS → WebSearch
- フィード本文: 要検証（XML応答確認済み、本文の有無は初回実行時に確認すること）
- 注目点: Geminiモデルリリース、Google I/O発表、プロダクト統合の公式アナウンス
- 頻度: 毎日確認
- 備考: リダイレクト先は `blog.google/innovation-and-ai/technology/ai/rss`。リダイレクトが解除された場合はURLを更新すること

## 高優先

### Google DeepMind Blog / Google Research
- URL: https://deepmind.google/discover/blog/
- RSS URL（優先）: https://research.google/blog/rss
- 検索キーワード（WebSearch用）: `Google DeepMind Gemini research 2026`
- 取得方法: RSS → WebSearch
- フィード本文: 要検証（XML応答確認済み、本文の有無は初回実行時に確認すること）
- 注目点: 新モデル（Gemini Ultra/Pro/Flash）の技術発表、ベンチマーク結果
- 頻度: 毎日確認
- 備考: カバー範囲は要検証。DeepMind固有の記事がフィードに含まれない場合は `deepmind.google/blog/rss.xml` の疎通を再調査すること

### Google Workspace Admin Release Calendar
- URL: https://support.google.com/a/table/7702199
- 取得方法: WebFetch → WebSearch
- 注目点: Workspace管理者向けリリース予定一覧。ロードマップに相当
- 頻度: 週1〜2回確認（更新頻度が低いため）

### Cursor Changelog
- URL: https://cursor.com/changelog
- 検索キーワード（WebSearch用）: `Cursor changelog new features 2026`
- 取得方法: WebFetch → WebSearch
- 注目点: 新機能、エージェント改善、IDE統合、料金変更
- 頻度: 毎日確認
- 備考: 2026-04-02時点でWebFetch成功（403解消）。再発時は `cursor-changelog.com/feed`（サードパーティRSS）への切り替えを検討

### Devin Release Notes
- URL: https://docs.devin.ai/release-notes/overview
- 検索キーワード（WebSearch用）: `Devin AI release notes update 2026`
- 取得方法: WebFetch → WebSearch
- 注目点: 新機能、モデル更新、料金変更
- 頻度: 毎日確認

### X (トレンド検索)
- 取得方法: WebSearch
- 検索キーワード例:
  - `AI new tool release`
  - `LLM update announcement`
  - `Claude Code`
  - `AI agent launch`
  - `AIツール 新機能`
  - `coding agent release`
- 注目点: 話題のAIツール、バズっている技術トピック
- 頻度: 毎日確認