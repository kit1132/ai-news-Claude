# 週次AIニュースサマリー — 2026年 第14週（3/28〜4/3）

対象日次ファイル: ai-news-2026-03-28 〜 ai-news-2026-04-03（7日分）

---

## 1. 今週のハイライト

1. **Cursor 3.0 リリース — VS Codeフォークから脱却した新UI**（4/2）: 複数エージェント並列実行、Design Mode、`/worktree`・`/best-of-n` コマンドなど、エージェント中心の新インターフェースを導入。有料開発者100万人突破も発表。

2. **Anthropic「Claude Mythos」モデル情報流出 & サイバーセキュリティ株急落**（3/26-30）: CMS設定ミスで未公開ブログ約3,000件が公開状態に。次世代モデル「Claude Mythos」（ティア名「Capybara」）の存在が判明し、CrowdStrike -7%、Palo Alto -6% など「Mythos Meltdown」が発生。

3. **Claude Code トークン消費バグが深刻化**（4/2）: Sentinel String Replacement バグでコストが10〜20倍に膨張、Max 5プラン（$100/月）で19分で枠を使い切る事例が報告。Anthropicが「チームの最優先事項」と認める。

4. **Anthropic IPO — 2026年Q4に$60B+調達の可能性**（3/27-30）: Goldman Sachs・JPMorgan・Morgan Stanleyと予備協議中。セカンダリー市場での評価額は$500-595B。年間売上$19Bに接近。

5. **Gemini 3 Pro ロールアウト開始**（4/3）: テキスト・画像・音声・動画のマルチモーダル推論が大幅改善。Deep Research でファイルアップロードにも対応。日本を含む4カ国の学生に7月まで無料アップグレード提供。

---

## 2. カテゴリ別まとめ

### Claude Code / Anthropic

- **Claude Code リリース**: v2.1.86（3/27）→ v2.1.87（3/29）→ v2.1.88（3/30）→ v2.1.89（4/1）→ v2.1.90（4/1）と急速なリリースサイクル。v2.1.88ではOpus 4.6の最大出力トークンを64kに引き上げ（上限128k）。v2.1.90では `/powerup` コマンド（インタラクティブレッスン）、auto modeのユーザー明示的境界無視バグの修正、レートリミットダイアログの無限ループ修正など。
- **トークン消費問題**: Sentinel String Replacement バグ（キャッシュプレフィックス破壊でコスト10-20倍）、Session Resume Token Drain バグ（再開時に65万トークン生成）が判明。回避策は旧バージョンへのダウングレード、Node.js経由実行、未使用MCPコネクタの切断。
- **ソースコード流出続報**: 幹部が「高速リリースサイクルに起因するプロセスエラー」と説明。GitHub上のコピー8,000件以上をDMCAテイクダウン。流出コードの98.4%はAIモデル本体ではなく制御・権限・マルチエージェント調整のエンジニアリング層。
- **Claude Mythos / Capybara**: サイバーセキュリティ能力が突出しており、少数の早期アクセス顧客と防御的セキュリティ用途でテスト中。
- **Anthropic vs Pentagon**: 仮差止命令獲得（3/26）。「古典的な修正第1条報復」と判示。政府側は控訴の構え。Bloomberg報道ではイラン有事でAnthropic技術が使用されたとの情報も。
- **市場シェア低下**: ビジネス採用シェアが29.1%（2025年3月）→ 13.3%（2026年3月）へ。中国AI企業の1/10以下の価格が要因。
- **オーストラリア政府とMOU締結**: AI安全研究・データセンター投資の覚書。AUD 300万ドル分のAPIクレジットを4機関に提供。
- **MCP月間SDKダウンロード9,700万回**: 16ヶ月で4,750%成長。
- **廃止予定**: Claude Haiku 3（4/19廃止）、Sonnet 4.5/4の1Mコンテキストbeta（4/30終了）。
- **Claude red team**: Opus 4.6でFirefox脆弱性22件を自律的に発見（Mozilla共同研究）。

### OpenAI

- **Codex プラグインシステム正式化**（3/27-30）: スキル・サードパーティ連携・MCPサーバー設定をバンドル化。GPT-5.4 miniがCodexアプリ・CLI・IDE拡張で利用可能に（リミット消費30%、3.3倍長い利用）。マルチエージェントv2も導入。
- **GPT-4o 完全廃止**（4/3）: Business/Enterprise/Eduの延長アクセスが終了し、全プランから完全削除。
- **GPT-5.4 mini & nano API リリース**: Chat Completions / Responses API対応。
- **ChatGPTに広告導入**: 会話内容ベースのパーソナライズ広告。広告データ削除・管理機能あり。
- **ChatGPT Atlas ブラウザ**（macOS）: ChatGPT内蔵Webブラウザ。
- **Model Spec公開**: モデルの行動規範・安全ポリシーの内部アプローチを詳述。
- **OpenAI Agents SDK**: WebSocketトランスポート対応、Python 3.9サポート終了。
- **Sora正式シャットダウン発表**: アプリ4/26、API 9/24に停止。Disney $1B提携解消。
- **OpenAI「Superapp」計画**: ChatGPT・Codex・Atlasブラウザを統合するMacデスクトップアプリを開発中。

### Google

- **Gemini 3 Pro ロールアウト開始**（4/3）: 全ユーザーに展開。Deep Research でファイルアップロード可能に。
- **Gemini 3 Flash がデフォルトモデルに**: PhD レベルの推論能力。
- **Gemini 3 Deep Think**: Ultra向けに提供開始。
- **Gemini API 課金体系変更**（4/1）: 月間支出上限を強制適用（Tier 1=$250〜）。
- **Gemini Deep Research API 公開**: HLE・BrowseCompで最高スコア。
- **Google Workspace 4月アップデート**: Gmail AI（Gemini 3搭載）、Slides Gemini強化、Meet on CarPlay、Vids→YouTube直接公開、AI Avatar カスタマイズ、Geminiフォーム作成21言語対応。
- **2026年3月コアアップデート**: AI生成コンテンツ検出精度向上。
- **DeepMind AGI認知フレームワーク**: AGI進捗を認知科学で測定。Kaggleハッカソン開催中（〜4/16）。

### 開発ツール（Cursor / Devin）

- **Cursor 3.0**（4/2）: VS Codeフォークから脱却した新UI。複数エージェント並列実行、Design Mode、`/worktree`・`/best-of-n` コマンド。有料開発者100万人突破。
- **Cursor BugBot Autofix**: 修正マージ率35%以上、解決率52%→76%。
- **Cursor Self-Hosted Cloud Agents**（3/25）: エージェントを自社インフラ上で実行。Brex・Money Forward・Notionが早期導入。
- **Cursor Composer 2 テクニカルレポート**（3/27）。
- **Devin PR Resuming**（4/1）: 別セッションの既存PRを引き継いで作業可能に。リアルタイムターミナル出力、GitHub Enterprise Server org対応。
- **Devin 3/27アップデート**: Preview features トグル、インラインファイルプレビュー、Focus Mode。

### 業界動向・セキュリティ

- **Claw Code**（4/2）: Python+Rust製OSSコーディングエージェント。公開数日で72,000 GitHub Stars。クリーンルーム実装を明示。
- **OpenClaw v2026.3.22**: OSSエージェントフレームワーク。GitHub星24.7万超。Ciscoがサードパーティスキルでデータ流出リスクを確認。
- **AIコーディングツール市場**: Claude Codeが全GitHubパブリックコミットの4%を占有（2026年末20%超の予測）。全主要AIラボが独自エージェントフレームワークを保有。
- **AIセキュリティツール**: Astrix Security（未承認AIエージェント検知）、Black Duck Signal（AI生成コードスキャン）、Palo Alto Prisma AIRS 3.0、Codenotary AgentMon。
- **Microsoft Security Dashboard for AI**: パブリックプレビュー。
- **Eclipse Theia / Open VSX Registry**: 月間3億ダウンロード突破。
- **AIコーディングツールのシステムプロンプト流出**: 28以上のツールのプロンプトを収集したリポジトリが134K Stars。
- **中国政府系ハッカーによるClaude Code悪用**: 約30組織を標的（検出済み）。中国AI企業による大規模モデル蒸留キャンペーンも告発。
- **RSAC 2026**: AIエージェント時代のセキュリティ課題が焦点。

### 国内動向

- **電通デジタル「AI For Growth Canvas」**: マーケティング特化型10種AIエージェント搭載（4/1提供開始）。
- **PeopleX「AgenticHR プラットフォーム」**: 人事領域の総合型AIエージェント基盤。
- **AIストーム × NTS**: コールセンター業務へのAI・自動化ノウハウ投入（4/1子会社化完了）。

---

## 3. 来週の注目予定

- **Claude Haiku 3 廃止**: 4/19。Haiku 4.5への移行が必要。
- **Google Workspace ゲストアカウント GA**: 4/13〜16。非Workspaceユーザーとのコラボが可能に。
- **Kaggle ハッカソン（DeepMind AGI）**: 〜4/16。賞金$200,000。
- **OpenAI Sora アプリ停止**: 4/26。
- **Sonnet 4.5/4 の1Mコンテキストbeta終了**: 4/30。Sonnet 4.6 / Opus 4.6への移行推奨。
- **Google Whisk → Flow 統合**: 4/30にWhisk終了。
- **GPT-5.5 / Claude 5 Mythos / DeepSeek-V4**: 4月中のトリプルリリースが予測されている。
- **Anthropic IPO**: Q4 2026（10月頃）に上場の可能性。

---

## 4. 改善メモ集約

### ソース取得の403エラー（全日共通・最重要）

全7日間を通じて、以下のソースが一貫して403エラーを返しており、WebSearchによるフォールバックが常態化している。

- Anthropic Blog（anthropic.com/news）
- Claude Release Notes（support.claude.com）
- Claude Code Changelog（code.claude.com） — WebFetchでは最新バージョンの反映にラグあり
- Cursor Changelog（cursor.com/changelog）
- Devin Release Notes（docs.devin.ai）
- OpenAI Blog / Platform Changelog / ChatGPT Release Notes
- Google The Keyword / Gemini Release Notes / DeepMind Blog / Workspace RSS
- Releasebot（releasebot.io）

**対応方針の検討事項**:
- WebFetchのUser-Agent制限が広範に適用されている可能性。WebSearchをプライマリ手段として運用する方針への切り替えを検討
- releasebot.io/updates/cursor をCursorのフォールバック、cognition.ai/blog をDevinのフォールバックとして追加検討
- Claude Code Changelogはキャッシュラグがあるため、WebSearch併用が必須

### 監視対象の追加検討

- OpenAI Codex / Platform系のソースURL追加（出現頻度が高い）
- Google Blog の監視対象追加（Gemini 3関連の情報が増加）
- Claude Mythos / Capybara の続報（正式発表・ベンチマーク等）を要注視
- Anthropic IPO関連の続報（OpenAIとの上場競争）も重要トピック

### その他

- ピーク時間帯制限の変更はユーザー体験に直結するため、今後の調整・撤回も追跡対象
- Gemini 3 Deep Thinkの正確なリリース日が不明瞭（3月下旬のどこか）。正確な日付の特定が困難なケースがある
- 403の発生が大半のソースに拡大しており、速報性・精度に限界あり。中長期的な代替取得手段の確立が必要
