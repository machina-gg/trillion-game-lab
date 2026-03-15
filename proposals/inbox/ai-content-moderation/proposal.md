# AI コンテンツモデレーション SaaS — 企画書

## ステータス

- 作成日: 2026-03-16
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

非英語圏の小〜中規模コミュニティ・プラットフォーム向けに、多言語・文化圏対応の AI コンテンツモデレーション API を月額 $29〜 で提供する SaaS。既存ツールが手薄な東南アジア・南アジア・ラテンアメリカの言語に特化し、文化的文脈を踏まえた高精度モデレーションを実現する。

## コンセプト

「言語の壁を越えたコミュニティ安全基盤」。

Hive Moderation や Sightengine などの既存ツールは英語・欧米文化圏に最適化されており、非英語圏ではモデレーション精度が低下する問題がある。インドネシア語・ヒンディー語・ポルトガル語（ブラジル）・タガログ語などに特化した AI モデルを提供し、小〜中規模プラットフォームでも月額 $29 から利用できる低コスト SaaS として差別化する。

## 解決する課題

**課題 1: 非英語コンテンツのモデレーション品質の低さ**

大手モデレーション AI は英語に最適化されており、非英語コンテンツへの過剰削除・見逃しが多発している。例えば Facebook はインド（同社最大ユーザー基盤）で 2019 年時点で 22 の公用語のうち 4 言語のみコンテンツモデレーションアルゴリズムがサポートしており、言語的空白が広がっていた（[Technology Science — Linguistic Inequity in Facebook Content Moderation, 2025](https://techscience.org/a/2025022501/)）。

**課題 2: 小規模プラットフォームには高すぎるコスト**

中小プラットフォーム向けのコンテンツモデレーション市場は最も速いペース（CAGR 約 15%）で成長しており、その背景には高コストな既存ソリューションを導入できない小規模事業者のニーズがある（[Mordor Intelligence — Content Moderation Market](https://www.mordorintelligence.com/industry-reports/content-moderation-market)）。エンタープライズ向けプランは月額 $5,000〜が相場で、小規模プラットフォームには現実的ではない。

**課題 3: 文化的文脈の欠如**

翻訳経由でモデレーションするアプローチでは文化的ニュアンスが失われ、誤検知・誤見逃しが発生する。ネスル語のスラングやタミル語の慣用表現など、文化圏固有の表現に対応できない。

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| 東南アジア系コミュニティアプリ | インドネシア・フィリピン・ベトナム語対応が必要 | 大手 API では精度が低い・英語中心 | 月間 1 万〜100 万 MAU のアプリ |
| インド系スタートアップ | ヒンディー語・タミル語・ベンガル語対応が必要 | インド語族向けの手頃な API がない | ローカルコミュニティ・教育アプリ |
| ブラジル・ラテンアメリカ系プラットフォーム | ポルトガル語（ブラジル方言）・スペイン語文化圏対応 | 英語 API では文化的スラングを誤検知 | ゲームコミュニティ・SNS |
| グローバル展開中の日本・韓国企業 | 多言語対応を一元化したい | ベンダーが複数に分散、コスト増大 | SaaS・ゲーム・EC プラットフォーム |

## 差別化ポイント

| 観点 | 既存プロダクト（Hive / Sightengine 等） | 当社プロダクト |
|------|-------------|-------------|
| 多言語対応 | 英語・欧州語中心。非英語は翻訳経由 | 東南アジア・南アジア・ラテンアメリカ語族にネイティブ対応 |
| 文化的文脈 | 翻訳によりニュアンス喪失 | 言語ごとに文化特化モデルを提供 |
| 価格 | $29〜$399/月（Sightengine）、$0.50/1K reqs（Hive）、スモールビジネスには高負担 | $29/月〜（月 10 万リクエスト含む）、スモールプランあり |
| オンボーディング | API キー取得後、設定が複雑 | ダッシュボードで言語・感度・ルールを GUI で設定可能 |
| 精度透明性 | 言語別精度データ非公開 | 言語別・カテゴリ別の F1 スコアを公開 |

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] **多言語テキストモデレーション API**: インドネシア語・ヒンディー語・ポルトガル語（ブラジル）・タガログ語・スペイン語の 5 言語対応。スパム・ヘイトスピーチ・暴力的表現を検出
- [ ] **ダッシュボード（GUI 設定）**: 言語選択・感度調整・カスタムキーワードを GUI で設定。技術知識不要でルール変更可能
- [ ] **Webhook / REST API**: 既存プラットフォームへの簡単統合。Node.js / Python SDK を提供
- [ ] **モデレーションログ・レポート**: 検出件数・カテゴリ別内訳・誤検知フラグを集計してダッシュボードに表示
- [ ] **ヒューマンレビュー連携**: 低確信度の判定をレビューキューに送信。外部レビュアーとの連携 API を提供

### Phase 2 以降

- [ ] 画像・動画モデレーション対応（多言語テキスト重畳への対応含む）
- [ ] 言語自動検出（言語を事前指定しなくても自動判別）
- [ ] カスタムモデルファインチューニング（顧客データで再学習）
- [ ] コンプライアンスレポート（EU DSA・インド IT Act 対応）
- [ ] リアルタイムチャットモデレーション SDK（React Native / Flutter）

## ビジネスモデル

**サブスクリプション（月額）+ 従量課金のハイブリッド**

| プラン | 月額 | 含まれるリクエスト数 | 超過料金 |
|--------|------|------|------|
| Starter | $29 | 100,000 リクエスト/月 | $0.40/1,000 |
| Growth | $99 | 500,000 リクエスト/月 | $0.30/1,000 |
| Scale | $299 | 2,000,000 リクエスト/月 | $0.20/1,000 |
| Enterprise | 要相談 | カスタム | カスタム |

**初期 14 日間無料トライアル**（クレジットカード不要）。

**収益予測**:

- Year 1: 顧客 50 社 × 平均 $80/月 = $4,800/月 = $57,600/年
- Year 2: 顧客 200 社 × 平均 $120/月 = $24,000/月 = $288,000/年
- Year 3: 顧客 500 社 × 平均 $150/月 = $75,000/月 = $900,000/年

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（コンテンツモデレーション全体） | $12.48 億 USD（2025） | [ResearchNester](https://www.researchnester.com/reports/content-moderation-services-market/7630) | 2026-03-16 |
| AI 自動化モデレーション市場 | $1.23 億 USD（2025）→ $6.8 億（2033） | [Verified Market Reports](https://www.verifiedmarketreports.com/product/ai-content-moderation-market/) | 2026-03-16 |
| CAGR（AI モデレーション） | 18.6% （2026〜2033） | [Verified Market Reports](https://www.verifiedmarketreports.com/product/ai-content-moderation-market/) | 2026-03-16 |
| CAGR（アジア太平洋地域） | 17.62%（2025〜2031） | [Mordor Intelligence](https://www.mordorintelligence.com/industry-reports/content-moderation-market) | 2026-03-16 |
| SAM（非英語圏 SME プラットフォーム向け） | 約 $2.5 億 USD（推定 TAM の 20%） | 推定 | 2026-03-16 |
| SOM（初期 3 年） | 約 $900 万 USD（SAM の 3.6%） | 推定 | 2026-03-16 |
| 世界インターネット利用者数 | 60.4 億人（2025 年 10 月） | [DataReportal](https://datareportal.com/global-digital-overview) | 2026-03-16 |

## 技術スタック（提案）

**フロントエンド（ダッシュボード）**

- Next.js 14 / TypeScript (strict) / Tailwind CSS
- Vercel でホスティング（無料〜$20/月）

**バックエンド / API**

- Node.js + Hono（軽量 REST API フレームワーク）
- PostgreSQL（Supabase 無料プラン〜$25/月）
- Redis（Upstash Serverless、リクエストキャッシュ）

**AI モデレーション基盤**

- MVP: OpenAI Moderation API（無料）+ GPT-4o-mini（多言語テキスト分析、$0.15/1M tokens）
- 言語特化処理: Hugging Face 公開モデル（インドネシア語 BERT 等）をサーバーレス推論で利用
- AWS Lambda / Vercel Functions でスケール対応

**月額インフラコスト試算（MVP 段階）**

| サービス | 費用 |
|---------|------|
| Vercel（Pro） | $20 |
| Supabase（Pro） | $25 |
| Upstash Redis | $0〜$10 |
| OpenAI API（Starter プラン 50 社想定） | $50〜$100 |
| **合計** | **$95〜$155/月** |

月額 $250 以下の制約に適合。

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| 大手（OpenAI・Google）が多言語対応を強化 | 高 | 文化特化モデルと低価格で差別化。ニッチ言語（タミル語・ジャワ語等）に特化 |
| モデレーション精度への法的責任 | 中 | 「支援ツール」として位置付け、最終判断は人間が行う旨を利用規約に明記 |
| 訓練データの入手困難（低リソース言語） | 中 | Hugging Face の公開データセット活用 + 顧客データでのファインチューニングオプション提供 |
| 競合の価格ダンピング | 低 | ダッシュボード・SDK の使いやすさとコミュニティサポートで粘着性を確保 |
| 為替リスク（途上国顧客） | 低 | ローカル通貨決済対応（Stripe の自動換算機能を利用） |

## データソース・調査方法

### 市場データ

- [ResearchNester — Content Moderation Services Market](https://www.researchnester.com/reports/content-moderation-services-market/7630) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Verified Market Reports — AI Content Moderation Market](https://www.verifiedmarketreports.com/product/ai-content-moderation-market/) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Mordor Intelligence — Content Moderation Market](https://www.mordorintelligence.com/industry-reports/content-moderation-market) — 信頼度: ★★★ — 取得日: 2026-03-16
- [DataReportal — Global Digital Overview 2025](https://datareportal.com/global-digital-overview) — 信頼度: ★★★ — 取得日: 2026-03-16

### 競合分析

- [GetStream — Top 8 Hive Moderation Alternatives](https://getstream.io/blog/hive-alternatives/) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Hive Moderation 公式 Pricing](https://thehive.ai/pricing) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Sightengine 公式 FAQ](https://sightengine.com/faq/pricing-for-text-moderation) — 信頼度: ★★★ — 取得日: 2026-03-16

### トレンド情報

- [TechPolicy.Press — Language Equity Gap in Content Moderation](https://www.techpolicy.press/how-measurement-can-fix-content-moderations-language-equity-gap/) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Technology Science — Linguistic Inequity in Facebook Content Moderation (2025)](https://techscience.org/a/2025022501/) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Imagga Blog — Future of Content Moderation Trends 2026](https://imagga.com/blog/the-future-of-content-moderation-trends-for-2026-and-beyond/) — 信頼度: ★★ — 取得日: 2026-03-16
- [Conectys — AI Content Moderation Trends 2026](https://www.conectys.com/blog/posts/ai-content-moderation-trends-for-2026/) — 信頼度: ★★ — 取得日: 2026-03-16

### 調査方法

WebSearch クエリ:

- `AI content moderation market size TAM 2025 2026`
- `content moderation SaaS competitors pricing Hive Moderation Two Hat Sightengine 2025`
- `multilingual content moderation non-English markets Southeast Asia India Brazil 2025`
- `content moderation gap multilingual small community platforms underserved market 2025`
- `internet users growth non-English speaking countries 2025 new users`
- `content moderation API pricing small community platform affordable 2025`

WebFetch で確認した公式サイト:

- `https://thehive.ai/pricing`（Hive Moderation 価格ページ）
- `https://getstream.io/blog/hive-alternatives/`（競合比較記事）
- `https://cdt.org/insights/content-moderation-in-the-global-south-...`（アクセス不可のためスキップ）
