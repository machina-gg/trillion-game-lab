# blog-factory SaaS — 企画書

## ステータス

- 作成日: 2026-02-22
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

キーワードを入力するだけで、AI がブログ記事を自動生成・WordPress へ自動投稿するオールインワン SaaS。エンジニアリング不要で、誰でも複数ブログを月額数千円から運営できる。

## コンセプト

blog-factory は、GitHub Actions + Claude API を組み合わせた「ブログ自動生成システム」を、非エンジニア向けに Web UI でラップした SaaS プロダクトである。

現在 blog-factory は CLI・GitHub ベースのシステムであり、利用者はエンジニアに限定されている。このシステムを SaaS 化することで、ブログで副収入を得たい個人・アフィリエイター・中小企業マーケターを対象に、プログラミング知識ゼロで AI ブログ自動化を利用可能にする。

**核心的な差別化**: 既存ツール（Transcope, AIブログくん等）はキーワードを入力するたびに 1 記事ずつ手動で生成するモデルである。blog-factory SaaS は「複数ブログ × 複数テーマ × 時間指定スケジュール」を一括設定し、以降は完全自動で動かし続ける「ブログ運営オペレーション全体の自動化」を提供する点が異なる。

## 解決する課題

### 課題 1: 技術的参入障壁

blog-factory の現システムは GitHub Actions の設定・API キーの管理・シェルスクリプトの理解が必要で、エンジニア以外は利用できない。日本のブロガー（推計 450 万人のアクティブユーザー、2025 年推計）の大多数は非エンジニアであり、このシステムの恩恵を受けられていない。

### 課題 2: 複数ブログ管理の煩雑さ

収益化のために複数テーマ・複数ブログを運営したい場合、手動運用では更新維持が困難。既存ツールは 1 記事ずつ手動で生成・投稿するフローが中心で、スケジューリングとマルチブログ管理が弱い。

### 課題 3: コスト最適化の難しさ

Claude API の従量課金は、使い方によって費用が大きく変動する。非エンジニアが直接 API を使うには設定コストが高く、適切な Haiku / Sonnet の使い分けもできていない。

### 課題 4: はてなブログ規約リスク

参考レポートが指摘するとおり、はてなブログの「自動生成記事への広告掲載禁止」規約はリスクが高い。SaaS 化の際は WordPress 連携をデフォルトとし、プラットフォーム規約リスクを排除した設計にする。

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| 副業アフィリエイター | 会社員・主婦。月 1〜10 万円の副収入目標 | 記事更新に時間がない。技術知識なし | 国内アフィリエイト市場に参加するのべ数百万人規模（市場規模 4,113 億円・2023 年度、矢野経済研究所） |
| 個人ブロガー | ゲーム・趣味テーマ。ファン収益化目標 | 継続更新が困難。SEO 対策の知識不足 | 日本のアクティブブロガー推計約 450 万人の一部（2025 年推計） |
| 中小企業マーケター | コンテンツマーケティング担当。1〜5 名チーム | ライター費用が高い。更新頻度が落ちる | SME のうち SaaS 未利用 66%（約 300 万社規模） |
| メディア運営者 | 複数テーマサイトを運営するメディア事業者 | 複数ブログの一元管理が困難 | 推計数万人規模 |

## 差別化ポイント

| 観点 | AIブログくん | Transcope | ChatGPT + 手動 | blog-factory SaaS |
|------|-------------|-----------|----------------|-------------------|
| 記事生成 | キーワード → 1 記事（都度手動実行） | キーワード → 1 記事（SEO強化） | 手動プロンプト | キーワードリスト → 複数記事一括 |
| WordPress 自動投稿 | あり | なし（手動コピペ） | なし | あり（複数ブログ対応） |
| スケジュール自動実行 | 継続稼働は可能だが日時指定不可（※1） | なし | なし | あり（日次・週次・時間指定） |
| 複数ブログ一元管理 | あり（サイト追加機能で対応）（※2） | なし | なし | あり（最大 10 ブログ・横断ダッシュボード） |
| コスト（月 50 記事） | 約 9,900 円（Starter プラン） | 約 11,000 円〜 | 約 1,000 円（時間コスト別） | 約 4,980 円（Growth プラン） |
| 技術知識要否 | 不要 | 不要 | 不要 | 不要 |
| テーマ別収益最適化レポート | なし | なし | なし | あり（テーマ × 収益性分析） |

※1 公式サイト FAQ・複数レビューサイトを確認。「投稿タイミングを自由に決められない」と明記されており、時間指定スケジューリングは非対応（[blogrou.com 調査](https://blogrou.com/aiblogkun/)、2026-02-22 確認）

※2 公式 FAQ で「複数ブログ運営可能」と明記されている。ただし横断的な一元ダッシュボードや横断レポート機能は提供されていない

**真の差別化ポイント**: AIブログくんはキーワードを都度投入して 1 記事ずつ生成するモデル。blog-factory SaaS は「キーワードリスト × スケジュール × 複数ブログ」をまとめて設定し、以降はゼロ操作で全ブログが自動更新され続ける「ハンズフリー運営」を実現する。また全ブログの PV・収益・コストを一画面で横断比較できるダッシュボードは、競合に存在しない機能である。

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] **ブログ登録・WordPress 接続**: WordPress REST API を使い、Web UI から接続情報を入力するだけで複数ブログを登録できる（最大 10 ブログ）
- [ ] **キーワード管理 + 記事スケジューリング**: ブログごとにキーワードリストと更新頻度（日次・週次）を設定。指定スケジュールで Claude API が記事を自動生成・投稿する
- [ ] **記事プレビュー & 承認フロー**: 自動生成された記事を公開前にプレビューし、1 クリックで承認または修正できる UI（Google のガイドライン対策として人間レビューステップを確保）
- [ ] **コスト管理ダッシュボード**: 月間の Claude API 使用コスト・生成記事数・PV 推移を可視化するダッシュボード
- [ ] **テーマ × 収益性レポート**: blog-factory の収益リサーチに基づき、テーマ別の推定 PV 単価・収益ポテンシャルをレポート表示（例: AI 系テーマは高単価、ゲーム系は競合が強い等）

### Phase 2 以降

- [ ] Google Search Console 連携（インデックス登録自動化・パフォーマンス可視化）
- [ ] アフィリエイトリンク自動挿入（Amazon アソシエイト・A8.net 対応）
- [ ] SNS 自動投稿（X / Threads）連携
- [ ] 記事品質スコアリング（Google E-E-A-T 基準の自動チェック）
- [ ] チームプラン（複数メンバーでの共同運営）

## ビジネスモデル

### サブスクリプションプラン

| プラン | 月額（税込） | 月間記事数上限 | ブログ数 | ターゲット |
|--------|------------|-------------|---------|-----------|
| Starter | 1,980 円 | 15 記事/月 | 1 ブログ | 副業ブロガー・試用 |
| Growth | 4,980 円 | 60 記事/月 | 3 ブログ | アフィリエイター |
| Pro | 9,800 円 | 200 記事/月 | 10 ブログ | メディア運営者 |

**コスト構造（Growth プランの場合）:**

Claude Haiku 4.5 API コスト（公式価格: 入力 $1/MTok・出力 $5/MTok, 1 ドル = 150 円換算）:

- 入力トークン: プロンプト約 2,000 トークン × $0.000001 × 150 = 0.3 円/記事
- 出力トークン: 生成本文約 3,000 トークン × $0.000005 × 150 = 2.25 円/記事
- **1 記事あたり API コスト: 約 2.6 円**

| 費用項目 | 金額 |
|---------|------|
| Claude Haiku 4.5 API（約 2.6 円 × 60 記事） | 約 156 円 |
| サーバー（Vercel + Supabase 無料枠） | 約 500 円 |
| GitHub Actions（記事生成実行基盤） | 約 300 円 |
| **合計コスト（1 ユーザー・Growth プラン）** | **約 956 円** |
| **粗利** | **4,980 − 956 = 4,024 円（粗利率 80.8%）** |

ソース: [Anthropic Claude API 公式料金ページ](https://platform.claude.com/docs/en/about-claude/pricing)（2026-02-22 確認）

### 損益分岐点

BEP の考え方（Growth プラン単独）:

- 固定費: インフラ固定費（Vercel Pro $20 + Supabase Pro $25 = 約 6,750 円/月）+ 開発・運用工数の機会コスト
- 変動費: 1 ユーザーあたり約 956 円/月
- 固定費を月 5 万円（インフラ + 最低限の運用時間）と仮定した場合、**約 13 契約で固定費回収**
- 月 10 万円規模（インフラ + 非常勤エンジニア相当）まで含めると、**約 25 契約で黒字化**
- Starter プラン（1,980 円、変動費約 450 円）単独の場合は **約 33 契約で黒字化**

※「月 10 万円」は Vercel・Supabase・GitHub Actions の従量課金 + 最小限の保守工数（週 2〜3 時間相当）を想定した目安

### 初期無料期間

- 14 日間フルトライアル（クレジットカード不要）
- 無料トライアル終了後、Starter プランに自動移行

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（グローバル AI コンテンツ生成市場） | USD 148 億（2024 年） → USD 801 億（2030 年） | [Grand View Research](https://www.grandviewresearch.com/industry-analysis/generative-ai-content-creation-market-report) | 2026-02-22 |
| TAM（AI コンテンツ作成市場・別推計） | USD 21.5 億（2024 年）→ USD 105.9 億（2033 年）、CAGR 19.4% | [Grand View Research](https://www.grandviewresearch.com/industry-analysis/ai-powered-content-creation-market-report) | 2026-02-22 |
| SAM（日本 SaaS 市場） | 約 1.4 兆円（2023 年）→ 2 兆円超（2027 年予測） | [ミノリティワークス](https://minority.works/blog/generative-ai-btob-saas-market-chaos-map-guide-2025/) | 2026-02-22 |
| SAM（日本 AI ライティングツール市場・推計） | 日本のアクティブブロガー約 450 万人 × 想定利用率 1% × ARPU 4,980 円 = 月約 2.24 億円 | 推定（ブロガー人口: [bonbankblog.com](https://bonbankblog.com/bloger-population)） | 2026-02-22 |
| SOM（初年度獲得目標） | 月 500 契約 × ARPU 4,980 円 = 月約 249 万円 | 推定 | 2026-02-22 |
| CAGR（AI コンテンツ作成市場） | 19.4%〜32.5% | [Grand View Research](https://www.grandviewresearch.com/industry-analysis/ai-powered-content-creation-market-report) / [generative AI segment](https://www.grandviewresearch.com/industry-analysis/generative-ai-content-creation-market-report) | 2026-02-22 |
| 日本のアクティブブロガー推計 | 約 450 万人（2025 年推計。閲覧中心を含む場合は 1,200 万人） | [bonbankblog.com](https://bonbankblog.com/bloger-population)（2025 年推計値） | 2026-02-22 |
| 国内アフィリエイト市場規模 | 4,113 億円（2023 年度）→ 4,382 億円見込み（2024 年度）、CAGR 約 7.2% | [矢野経済研究所](https://www.yano.co.jp/press-release/show/press_id/3746) | 2026-02-22 |

## 技術スタック（提案）

### フロントエンド

- **Next.js 14**（App Router）+ **TypeScript** (strict)
- **Tailwind CSS** でダッシュボード UI
- **Shadcn/ui** コンポーネントライブラリ

### バックエンド

- **Supabase**（PostgreSQL + 認証 + Row Level Security）
- **Vercel** でホスティング（無料枠→有料へスケール）
- **GitHub Actions** で記事生成ジョブ実行（既存 blog-factory ロジックを再利用）

### AI / 外部連携

- **Claude API** (Haiku 4.5 で低コスト記事生成、高品質オプションは Sonnet)
- **WordPress REST API** で自動投稿
- **Google Search Console API** で PV・インデックス管理（Phase 2）

### コスト試算（月額・サービス全体、100 ユーザー規模）

| 項目 | 費用 | 備考 |
|------|------|------|
| Vercel Pro | $20（約 3,000 円） | チーム機能・帯域含む |
| Supabase Pro | $25（約 3,750 円） | DB + 認証 + ストレージ |
| Claude API（Haiku 4.5）100 ユーザー × 60 記事 × 2.6 円 | 約 15,600 円 | 公式価格から計算 |
| GitHub Actions | 約 5,000 円 | ジョブ実行時間分 |
| **合計（100 ユーザー Growth プラン規模）** | **約 27,350 円/月** | |

→ 100 ユーザー Growth プランで月収 49.8 万円 / コスト約 2.7 万円 = **粗利率 約 94.5%**

**月額 $250（約 37,500 円）制約について**: MVP フェーズ（ユーザー数問わずインフラ固定費）は月 6,750 円（Vercel + Supabase のみ）。ユーザー増加に比例して API コストがスケールするが、収益もそれ以上にスケールするため制約問題は生じない。

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| Google AI コンテンツペナルティ（2025 年ガイドライン改定）| 高 | MVP に「承認フロー（人間レビューステップ）」を組み込み、完全自動化ではなく「AI 支援」と位置付ける |
| はてなブログ規約（自動生成記事への広告掲載禁止）| 高（回避済み） | WordPress 連携のみ提供。はてなブログは対応外として規約問題を排除する |
| Claude API コスト増大（Sonnet 利用増加）| 中 | デフォルト Haiku 4.5 に固定。Sonnet オプションは上位プランのみで提供 |
| 競合（AIブログくん）の機能拡張 | 中 | AIブログくんは既に複数ブログ管理に対応。差別化は「時間指定スケジューリング + 横断ダッシュボード + 収益最適化レポート」の深化で維持。早期ユーザー獲得でスイッチングコストを高める |
| SEO の長期効果不確実性 | 中 | 収益期待値の透明な開示（月 6〜14 ヶ月で黒字化見込み）。過度な期待を避ける LP 設計 |
| Amazon アソシエイト / AdSense 審査落ち | 中 | ユーザー向けに「審査通過チェックリスト」を提供。記事品質を高めるプロンプト設計を継続改善 |
| 初期ユーザー獲得コスト | 高 | blog-factory の GitHub リポジトリ読者・既存エンジニアユーザーをアーリーアダプターとして無料招待。口コミ拡散を狙う |

## データソース・調査方法

### 市場データ

- [Grand View Research — AI-Powered Content Creation Market Report](https://www.grandviewresearch.com/industry-analysis/ai-powered-content-creation-market-report) — 信頼度: ★★★ — 取得日: 2026-02-22
- [Grand View Research — Generative AI in Content Creation Market](https://www.grandviewresearch.com/industry-analysis/generative-ai-content-creation-market-report) — 信頼度: ★★★ — 取得日: 2026-02-22
- [The Business Research Company — AI Powered Content Creation Market 2025](https://www.thebusinessresearchcompany.com/report/ai-powered-content-creation-global-market-report) — 信頼度: ★★★ — 取得日: 2026-02-22
- [Statista — SaaS Japan Market Forecast](https://www.statista.com/outlook/tmo/public-cloud/software-as-a-service/japan) — 信頼度: ★★★ — 取得日: 2026-02-22

### 競合分析

- [AIブログくん 公式サイト](https://www.ai-blogkun.com/) — 信頼度: ★★★ — 取得日: 2026-02-22
- [Boxil — AIライティングツール比較](https://boxil.jp/mag/a10168/) — 信頼度: ★★★ — 取得日: 2026-02-22
- [haruchiko.com — AIブログくん vs BLOGAI 比較](https://haruchiko.com/ai-blogkun-vs-blogai/) — 信頼度: ★★ — 取得日: 2026-02-22
- [SHIFT AI TIMES — AIブログ記事自動化ツール5選](https://shift-ai.co.jp/blog/14365/) — 信頼度: ★★ — 取得日: 2026-02-22
- [Transcope 公式 — SEOに強いブログAIツール14選](https://transcope.io/column/ai-blog-tool) — 信頼度: ★★ — 取得日: 2026-02-22

### トレンド情報

- [矢野経済研究所 — アフィリエイト市場に関する調査（2025年）](https://www.yano.co.jp/press-release/show/press_id/3746) — 信頼度: ★★★ — 取得日: 2026-02-22（2023 年度市場規模 4,113 億円・2028 年度予測 5,835 億円・CAGR 7.2% を引用）
- [bonbankblog.com — 日本のブログ人口推計（2025 年版）](https://bonbankblog.com/bloger-population) — 信頼度: ★★ — 取得日: 2026-02-22（アクティブブロガー約 450 万人推計を引用）
- [Anthropic — Claude API 公式料金ページ](https://platform.claude.com/docs/en/about-claude/pricing) — 信頼度: ★★★ — 取得日: 2026-02-22（Haiku 4.5: 入力 $1/MTok・出力 $5/MTok を引用）
- [nihonium.io — Japan SaaS Market Trends 2025](https://nihonium.io/10-data-trends-shaping-japans-saas-market-in-2025/) — 信頼度: ★★ — 取得日: 2026-02-22

### 参考レポート

- `/Users/akihiroito/personalwork/git/blog-factory/docs/revenue-research-report.md` — blog-factory の収益・コスト・リスク構造の詳細分析（コスト試算・収益予測・はてなブログ規約リスクの根拠として使用）

### 調査方法

- WebSearch クエリ: "AI blog automation SaaS market size 2025 TAM content generation"
- WebSearch クエリ: "AI content generation SaaS competitors 2025 pricing Jasper Copy.ai WriteSonic"
- WebSearch クエリ: "ブログ自動生成 SaaS 非エンジニア向け 2025 日本市場 競合"
- WebSearch クエリ: "AIライティングツール 日本 月額 比較 2025 ブログ自動化 サービス"
- WebSearch クエリ: "日本 ブロガー人口 2025 アフィリエイター ブログ運営者 推計"
- WebFetch: AIブログくん公式サイト（スケジュール機能・複数ブログ対応を直接確認）、Grand View Research マーケットレポート、Boxil 比較記事、SHIFT AI TIMES、blogrou.com（AIブログくん機能詳細）、矢野経済研究所プレスリリース、Anthropic Claude API 公式料金ページ
