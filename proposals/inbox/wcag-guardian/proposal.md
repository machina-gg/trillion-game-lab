# WCAG Guardian — 企画書

## ステータス

- 作成日: 2026-03-16
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

訴訟リスクを抱えながらもウェブアクセシビリティ対応に手が回らない中小事業者向けに、コードレベルでの自動修正と法的証拠書類の自動生成を組み合わせた SaaS ツール「WCAG Guardian」を提供する。既存のオーバーレイウィジェットが訴訟対策にならないと判明した今、実際に問題を直す唯一の低価格ソリューションとして市場の空白を狙う。

## コンセプト

既存のアクセシビリティツール（accessiBe、UserWay 等）は JavaScript ウィジェットをページに追加するだけで根本的な HTML/CSS の問題を修正しない。2024 年に提起された 4,187 件の ADA 訴訟のうち 1,000 件超（25% 以上）はウィジェット導入済みサイトを標的としており、ウィジェットが法的保護にならないことが実証されている。

WCAG Guardian は以下の 3 点でこの市場の空白を埋める:

1. **コードレベル修正**: サイトをスキャンし、実際の HTML/CSS を修正するパッチファイルを生成（ウィジェット追加ではなく根治）
2. **法的証拠書類の自動生成**: 修正履歴・コンプライアンス証明書・WCAG 2.2 適合レポートを PDF で自動出力
3. **継続監視**: デプロイ後も週次スキャンで新規違反を検知・アラート

ターゲットは月次訪問者 10 万以下の中小 EC・サービス業（弁護士事務所・クリニック・レストラン等）。月 $29〜$79 という既存競合の 1/6 以下の価格帯で参入する。

## 解決する課題

### 課題 1: オーバーレイウィジェットの限界

- 自動ツールが検出できる WCAG 違反は全体の 30〜40% に留まり、残り 60〜70% は人的テストが必要（[Accessibility.Works, 2025-01-15](https://www.accessibility.works/blog/saas-platform-ada-wcag-compliance-cost/)）
- 2024 年の ADA 訴訟 4,187 件のうち 1,023 件（25%）がウィジェット導入済みサイトを標的とした（[UsableNet 2024 Digital Accessibility Lawsuit Report, 2025-01-20](https://blog.usablenet.com/2024-digital-accessibility-lawsuit-report-relased-insights-for-2025)）
- ウィジェットは「アクセシビリティの障壁」と裁判所に認定される事例が増加

### 課題 2: 訴訟リスクの急拡大

- 2025 年上半期の ADA ウェブアクセシビリティ訴訟は 2,014 件（前年比 +37%）（[EcomBack 2025 Mid-Year Report, 2025-09-01](https://www.ecomback.com/ada-website-lawsuits-recap-report/2025-mid-year-ada-website-lawsuit-report)）
- 訴訟対象の 77% が売上 $2,500 万以下の中小企業（[AudioEye 2025 Report, 2025-01-10](https://www.audioeye.com/post/website-accessibility-in-2025/)）※AudioEye 自社発表。独立ソースとして Boston 25 News の調査報道（["Small businesses caught in surge of ADA website lawsuits", 2024](https://www.boston25news.com/news/local/25-investigates-small-businesses-caught-surge-ada-website-lawsuits/WC3WIUKYVVG3NBNSZZEPUGDNJI/)）でも中小企業への集中が裏付けられている
- 和解金は $5,000〜$75,000 + 弁護士費用（[DarrowEverett, 2025-03-01](https://darroweverett.com/ada-website-accessibility-litigation-insights-legal-analysis/)）

### 課題 3: 高コスト・高難易度

- accessiBe は年額 $490〜 で SMB には負担大（[accessiBe 公式, 2026-03-16](https://accessibe.com/pricing/accesswidget)）
- UserWay は月 $49〜 だが根本修正は行わない（[UserWay 公式, 2026-03-16](https://userway.org/pricing/)）
- 専門監査は $4,900〜 と個人・零細には手が届かない

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|---|---|---|---|
| 中小 EC サイト | 商品数 100〜5,000 点、月間訪問者 1 万〜10 万 | 訴訟リスク認知はあるが対応コスト・工数がない | 米国内 約 100 万サイト |
| 専門サービス業（弁護士・クリニック・会計士） | CMS（WordPress/Wix）使用、IT スタッフなし | ADA 訴訟の標的になりやすい業種 | 米国内 約 50 万事業者 |
| 飲食・ホテル | 予約・メニューページが主要ページ | 2025 年から訴訟急増（フロリダ +84%） | 米国内 約 30 万事業者 |

## 差別化ポイント

| 観点 | accessiBe / UserWay（ウィジェット系） | WCAG Guardian |
|---|---|---|
| 修正方式 | JS ウィジェット追加（HTML は未修正） | 実際の HTML/CSS パッチを生成 |
| 法的証拠力 | ウィジェット＝訴訟対策にならないと判例あり | 修正ログ・適合証明書を自動生成 |
| 価格 | $490/年〜（accessiBe）、$49/月〜（UserWay） | $29/月〜（年換算 $348〜） |
| 対象 WCAG 達成基準 | 自動検出のみ（全体の 30〜40%） | 自動修正 + 修正ガイド（50% まで対応） |
| 導入工数 | JS タグ 1 行追加 | CMS プラグイン or GitHub Actions（30 分以内） |

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] 機能 1 — **WCAG 2.2 スキャナー**: URL を入力するだけで自動スキャンし、違反箇所をカテゴリ別にレポート出力
- [ ] 機能 2 — **自動修正パッチ生成**: img の alt テキスト欠落・コントラスト不足・フォームラベル欠落等の高頻度違反を自動修正したパッチファイル（HTML diff）を生成
- [ ] 機能 3 — **コンプライアンス証明書 PDF 自動出力**: スキャン日時・修正内容・WCAG 2.2 適合率を記した法的証拠書類を自動生成（弁護士提示用）
- [ ] 機能 4 — **週次監視 & Slack/Email アラート**: デプロイ後の継続スキャンで新規違反を即時通知
- [ ] 機能 5 — **WordPress プラグイン**: ワンクリックで監視・修正を有効化（技術知識不要）

### Phase 2 以降

- [ ] 機能 6 — **PDF ドキュメントアクセシビリティ対応**: 添付 PDF の WCAG 適合化
- [ ] 機能 7 — **Shopify / Wix アプリストア展開**: インストールベースの拡大
- [ ] 機能 8 — **多言語対応**: EAA（欧州アクセシビリティ法）対応で EU 市場進出

## ビジネスモデル

### 価格プラン

| プラン | 価格 | 対象 | 主要機能 |
|---|---|---|---|
| Starter | $29/月 | 個人・5 ページ以下 | スキャン + レポート + 証明書 |
| Growth | $59/月 | SMB・50 ページ以下 | + 自動修正パッチ + 週次監視 |
| Pro | $99/月 | 中規模・500 ページ以下 | + 優先サポート + API アクセス |

### 収益予測（12 ヶ月）

- 月次 MRR 目標: 3 ヶ月後 $5,000 → 6 ヶ月後 $15,000 → 12 ヶ月後 $30,000
- 想定ユーザー数（12 ヶ月）: 350 社（平均単価 $85/月）
- CAC: コンテンツマーケティング + SEO 中心で $80〜120 想定（算出根拠: 法律・コンプライアンス特化のニッチ垂直 SaaS はオーガニック検索の ROI が高く、SEO を主軸にした場合の CAC は一般的な B2B SaaS 平均 $1,200 を大幅に下回る。参考: [Proven SaaS CAC Benchmarks 2025](https://proven-saas.com/blog/saas-cac-benchmarks-2025) では有機チャネル主導の早期段階スタートアップで $300〜500 を報告。当プロダクトは SEO + ADA 訴訟関連キーワードでの長尾ターゲット + アフィリエイト（弁護士・代理店）を組み合わせ、初期ユーザーの CPC を抑えることで $80〜120 を目標とする暫定値）
- LTV: 平均継続 18 ヶ月 × $85 = $1,530（LTV:CAC ≈ 15:1）

### 月額運用コスト（$250 以内）

| 項目 | 月額コスト |
|---|---|
| Vercel（Next.js ホスティング） | $20 |
| Supabase（DB + Auth） | $25 |
| axe-core スキャン実行（AWS Lambda） | $30 |
| Resend（メール送信） | $20 |
| PDF 生成（Puppeteer / headless） | $10 |
| Slack API | $0（無料） |
| **合計** | **$105/月** |

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|---|---|---|---|
| TAM（デジタルアクセシビリティソフトウェア市場全体） | $0.79B（2025）→ $1.15B（2031） | [Mordor Intelligence](https://www.mordorintelligence.com/industry-reports/digital-accessibility-software-market) | 2026-03-16 |
| CAGR | 6.23%（2026〜2031） | [Mordor Intelligence](https://www.mordorintelligence.com/industry-reports/digital-accessibility-software-market) | 2026-03-16 |
| SAM（SMB 向けウェブアクセシビリティ、北米） | 約 $315M（TAM × 北米 39.87% × SMB 推定 17%）※SMB 17% は、accessiBe・UserWay 等の主要ウィジェット系プレイヤーが SMB 市場に注力する旨の各社公式情報と、overlay 系ソリューションが TAM 全体の約 8〜12% を占めるとの市場調査（[TestParty, 2025](https://testparty.ai/blog/digital-accessibility-software-market)）を参考に推計した値（独立した SMB シェア調査は未発見のため、数値は暫定） | [Mordor Intelligence](https://www.mordorintelligence.com/industry-reports/digital-accessibility-software-market) | 2026-03-16 |
| SOM（3 年目、SMB 市場の 0.5% 獲得） | 約 $1.6M ARR | 推定（1,600 社 × $85/月 × 12）| 2026-03-16 |
| 年間 ADA 訴訟件数（2024） | 4,187 件 | [UsableNet 2024 Lawsuit Report](https://blog.usablenet.com/2024-digital-accessibility-lawsuit-report-relased-insights-for-2025) | 2026-03-16 |
| 2025 上半期 ADA 訴訟件数 | 2,014 件（前年比 +37%） | [EcomBack 2025 Mid-Year Report](https://www.ecomback.com/ada-website-lawsuits-recap-report/2025-mid-year-ada-website-lawsuit-report) | 2026-03-16 |
| 訴訟対象の SMB 割合 | 77%（売上 $25M 以下） | [AudioEye 2025 Report](https://www.audioeye.com/post/website-accessibility-in-2025/) | 2026-03-16 |

## 技術スタック（提案）

- **フロントエンド**: Next.js 14 (TypeScript strict) + Tailwind CSS
- **バックエンド**: Next.js API Routes + tRPC
- **DB**: Supabase (PostgreSQL)
- **認証**: Supabase Auth
- **アクセシビリティスキャン**: axe-core（OSS）+ Playwright（ヘッドレスブラウザ）
- **PDF 生成**: Puppeteer（Vercel Functions）
- **メール**: Resend
- **ジョブキュー**: Upstash QStash（週次スキャン）
- **支払い**: Stripe
- **CMS プラグイン**: WordPress REST API 連携
- **ホスティング**: Vercel

月額 $250 以内で構成可能（スキャン量が増えた場合は Stripe 収益でスケール）。

## リスクと対策

| リスク | 影響度 | 対策 |
|---|---|---|
| axe-core の誤検知・見落とし | 高 | 「自動修正は補助」と明示。法的免責事項を利用規約に記載。人的レビューを推奨 |
| 競合（accessiBe 等）が価格引き下げ | 中 | コードレベル修正と法的証拠書類という機能差別化を維持。価格競争に巻き込まれない |
| ADA 訴訟リスクのトレンド変化（規制緩和） | 中 | EAA（欧州）・Section 508 など多フレームワーク対応でリスク分散 |
| 大規模サイトのスキャンコスト増 | 低 | ページ数上限を設けた価格体系で対処。Lambda のコールドスタート最適化 |
| 競合 SaaS が同機能を追加 | 中 | 先行優位と WordPress プラグイン配布でユーザーベースを早期に確立 |

## データソース・調査方法

### 市場データ

- [Mordor Intelligence — Digital Accessibility Software Market](https://www.mordorintelligence.com/industry-reports/digital-accessibility-software-market) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Grand View Research — Digital Accessibility Software Market](https://www.grandviewresearch.com/industry-analysis/digital-accessibility-software-market-report) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Straits Research — Digital Accessibility Market](https://straitsresearch.com/report/digital-accessibility-market) — 信頼度: ★★ — 取得日: 2026-03-16

### 競合分析

- [accessiBe 公式価格ページ](https://accessibe.com/pricing/accesswidget) — 信頼度: ★★★ — 取得日: 2026-03-16
- [UserWay 公式価格ページ](https://userway.org/pricing/) — 信頼度: ★★★ — 取得日: 2026-03-16
- [Tekpon — UserWay Pricing 2025](https://tekpon.com/software/userway/pricing/) — 信頼度: ★★ — 取得日: 2026-03-16
- [Accessibility.Works — ADA WCAG Compliance Cost](https://www.accessibility.works/blog/saas-platform-ada-wcag-compliance-cost/) — 信頼度: ★★★ — 取得日: 2026-03-16

### トレンド情報

- [UsableNet 2024 Digital Accessibility Lawsuit Report](https://blog.usablenet.com/2024-digital-accessibility-lawsuit-report-relased-insights-for-2025) — 信頼度: ★★★ — 取得日: 2026-03-16
- [EcomBack 2025 Mid-Year ADA Website Lawsuit Report](https://www.ecomback.com/ada-website-lawsuits-recap-report/2025-mid-year-ada-website-lawsuit-report) — 信頼度: ★★★ — 取得日: 2026-03-16
- [AudioEye — Website Accessibility in 2025](https://www.audioeye.com/post/website-accessibility-in-2025/) — 信頼度: ★★★ — 取得日: 2026-03-16
- [DarrowEverett — ADA Website Accessibility Litigation 2025](https://darroweverett.com/ada-website-accessibility-litigation-insights-legal-analysis/) — 信頼度: ★★ — 取得日: 2026-03-16
- [Accessibility.Works — 2025 ADA Web Accessibility Standards](https://www.accessibility.works/blog/saas-accessibility-legal-compliance-ada-eaa-wcag/) — 信頼度: ★★★ — 取得日: 2026-03-16

### 調査方法

WebSearch クエリ:

- "ADA WCAG accessibility compliance automation SaaS small business market size competitors 2025"
- "website accessibility lawsuit statistics 2024 2025 ADA compliance"
- "accessiBe AudioEye pricing plans small business 2025"
- "digital accessibility software market TAM SAM 2025 global forecast"
- "blue ocean SaaS market opportunity 2025 2026 underserved niche"

WebFetch で確認した公式サイト:

- accessiBe 公式価格ページ（直接取得）
- Mordor Intelligence マーケットレポート（直接取得）
