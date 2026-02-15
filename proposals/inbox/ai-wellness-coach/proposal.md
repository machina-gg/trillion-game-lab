# AI Wellness Coach — 企画書

## ステータス

- 作成日: 2026-02-16
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

AI Wellness Coach は、フィットネスと栄養を統合したパーソナルコーチングアプリです。ユーザーは月額 $39 で、AI が個別最適化したワークアウトプラン、食事プラン、リアルタイムフィードバックを受け取り、従来のパーソナルトレーナー（月額 $200-500）の1/5以下のコストで同等のサポートを得られます。

## コンセプト

フィットネスと栄養の管理は健康的な生活の両輪ですが、従来のパーソナルトレーナーや栄養士は高額で継続が困難です。また、既存のフィットネスアプリは「ワークアウトのみ」「栄養のみ」と分断されており、統合的なアプローチが欠けています。

AI Wellness Coach は、AI がユーザーの目標（減量、筋肉増強、健康維持など）、体質、ライフスタイル、食事の好みを学習し、パーソナライズされたワークアウトと食事プランを自動生成します。さらに、ウェアラブルデバイスと連携し、リアルタイムでフォームチェックや栄養アドバイスを提供します。

## 解決する課題

- **高額なパーソナルトレーナー費用**: 月額 $200-500 と高額で、継続的な利用が困難
- **分断されたアプローチ**: フィットネスと栄養が別々に管理され、統合的な健康管理ができない
- **汎用的なプラン**: 既存アプリは一般的なプランを提供するだけで、個別最適化されていない
- **継続の困難**: モチベーション維持が難しく、多くのユーザーが数週間で離脱する
- **フィードバック欠如**: 自己流のトレーニングではフォームが悪く、怪我のリスクがある

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| フィットネス初心者（20-40歳） | ジムに行ったことがない、何から始めればいいかわからない | 高額なパーソナルトレーナー、ジムへのハードル、継続できない | 世界で約10億人（フィットネスに興味があるが始められていない層） |
| ダイエット志向層（25-50歳） | 減量・体型維持が目標、食事管理が苦手 | カロリー計算が面倒、何を食べればいいかわからない、リバウンドしやすい | 世界で約15億人（BMI 25以上の過体重・肥満層） |
| アスリート・上級者（20-45歳） | 筋肉増強・パフォーマンス向上が目標 | 高度なトレーニングプランが必要、栄養管理が複雑、データ分析が不足 | 世界で約5億人（定期的にトレーニングしている層） |

## 差別化ポイント

| 観点 | 既存プロダクト（MyFitnessPal, Noom） | AI Wellness Coach |
|------|-------------|-------------|
| **統合アプローチ** | MyFitnessPal: 栄養のみ、Noom: ダイエット重視 | フィットネス + 栄養 + メンタルウェルネスの統合管理 |
| **価格** | MyFitnessPal: $19.99/年、Noom: $70/月 | $39/月（フィットネス + 栄養の両方） |
| **AI パーソナライゼーション** | MyFitnessPal: 基本的なカロリー計算、Noom: 行動変容重視 | AI が目標・体質・ライフスタイルを学習し、毎週プランを自動調整 |
| **リアルタイムフィードバック** | なし（記録のみ） | AI がカメラでフォームチェック、栄養分析を写真から自動実行 |
| **ウェアラブル統合** | MyFitnessPal: 基本的な連携、Noom: なし | Apple Watch、Fitbit、Whoop などと完全統合、心拍数・睡眠・回復データを活用 |
| **コミュニティ** | 限定的 | 同じ目標を持つユーザーとのチャレンジ、モチベーション維持機能 |

**主な差別化要素:**
- **統合プラットフォーム**: フィットネス、栄養、メンタルウェルネスを一つのアプリで管理
- **AI フォームチェック**: スマホカメラでワークアウトのフォームをリアルタイム分析し、怪我を防止
- **写真ベース栄養分析**: 食事の写真を撮るだけで、AI が栄養素を分析し、改善提案を提供
- **適応型プラン**: ユーザーの進捗、疲労度、ストレスレベルに応じて毎週プランを自動調整
- **手頃な価格**: パーソナルトレーナーの1/5以下のコストで同等のサポート

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] **AI ワークアウトプラン**: 目標（減量、筋肉増強、健康維持）に応じたパーソナライズドプランを自動生成。500種類以上のエクササイズライブラリ
- [ ] **AI 栄養プラン**: 写真ベースの食事トラッキング、AI が栄養素を分析し、改善提案を提供。カロリー、マクロ栄養素（タンパク質、炭水化物、脂質）の自動計算
- [ ] **リアルタイムフォームチェック**: スマホカメラでワークアウト中のフォームを分析し、リアルタイムで修正提案（AI ビデオ解析）
- [ ] **ウェアラブル統合**: Apple Watch、Fitbit との連携で心拍数、消費カロリー、睡眠データを取得
- [ ] **進捗トラッキング**: 体重、体脂肪率、筋肉量、ワークアウト履歴の可視化。週次・月次レポート生成

### Phase 2 以降

- [ ] **ライブコーチング**: プレミアムプラン（$99/月）で月4回のビデオコーチングセッション（人間トレーナー）
- [ ] **コミュニティチャレンジ**: 同じ目標を持つユーザーとのグループチャレンジ、リーダーボード、モチベーション維持
- [ ] **食事配達統合**: Uber Eats、DoorDash などと連携し、栄養プランに基づいた食事を提案・注文
- [ ] **回復・睡眠最適化**: 睡眠データと疲労度を分析し、リカバリープラン（ストレッチ、マッサージ、休息日）を提案
- [ ] **AR ワークアウト**: AR グラスを使ったワークアウトガイド、フォームの3D可視化

## ビジネスモデル

**収益モデル:**
- **ベーシックプラン**: $39/月 — AI ワークアウト、AI 栄養プラン、フォームチェック、ウェアラブル統合、進捗トラッキング
- **プレミアムプラン**: $99/月 — ベーシック機能 + 月4回の人間トレーナーセッション + 食事配達統合 + 回復最適化
- **年間プラン**: $399/年（ベーシック）、$999/年（プレミアム）— 月額換算で約15%割引
- **企業向けプラン**: $25/ユーザー/月（50名以上）— 従業員の健康福利厚生として提供

**収益予測:**
- Year 1: 15,000ユーザー（85%ベーシック、15%プレミアム）→ 年間収益 $7.7M
- Year 2: 75,000ユーザー → 年間収益 $38.5M
- Year 3: 200,000ユーザー → 年間収益 $102.8M

**LTV（顧客生涯価値）:**
- ベーシックプラン: $468（平均継続期間12ヶ月）
- プレミアムプラン: $1,188（平均継続期間12ヶ月）

**CAC（顧客獲得コスト）:**
- ターゲット: $40-60/ユーザー（SNS広告、インフルエンサーマーケティング、コンテンツマーケティング）

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（フィットネスアプリ） | $45.45 billion（2035年予測） | [Towards Healthcare](https://www.towardshealthcare.com/insights/fitness-app-market-sizing) | 2026-02-16 |
| SAM（2026年） | $13.92 billion | [Grand View Research](https://www.grandviewresearch.com/industry-analysis/fitness-app-market) | 2026-02-16 |
| TAM（AI栄養） | $4.26 billion（2032年予測） | [DataM Intelligence](https://www.prnewswire.com/news-releases/ai-in-personalized-nutrition-market-to-reach-usd-4-26-billion-by-2032--driven-by-predictive-analytics-deep-learning--real-time-dietary-intelligence--datam-intelligence-302617136.html) | 2026-02-16 |
| SAM（栄養アプリ2026年） | $6.94 billion | [Towards Healthcare](https://www.towardshealthcare.com/insights/diet-and-nutrition-apps-market-sizing) | 2026-02-16 |
| SOM（初年度獲得可能市場） | $100 million（推定0.5%シェア） | 推定 | 2026-02-16 |
| CAGR（フィットネス） | 14.15% | [Towards Healthcare](https://www.towardshealthcare.com/insights/fitness-app-market-sizing) | 2026-02-16 |
| CAGR（AI栄養） | 18.19% | [DataM Intelligence](https://www.prnewswire.com/news-releases/ai-in-personalized-nutrition-market-to-reach-usd-4-26-billion-by-2032--driven-by-predictive-analytics-deep-learning--real-time-dietary-intelligence--datam-intelligence-302617136.html) | 2026-02-16 |

**追加データ:**
- モバイルフィットネスアプリ市場は2026年に$14.7Bに到達予測（[Robeco](https://www.robeco.com/en-int/insights/2026/02/consumer-trends-in-2026-safety-security-and-the-wearables-comeback)、2026-02-16取得）
- MyFitnessPal は2億人以上のユーザー、年間収益 $310M（[Business of Apps](https://www.businessofapps.com/data/myfitnesspal-statistics/)、2026-02-16取得）
- Noom はプレミアム価格 $39.99/月（6ヶ月プラン）で350万人のユーザー（[Pocketful of Joules](http://www.pocketfulofjoules.com/my-thoughts-on-noom-vs-myfitnesspal/)、2026-02-16取得）

## 技術スタック（提案）

- **フロントエンド**: Next.js 14, TypeScript, Tailwind CSS
- **バックエンド**: Node.js, Prisma, PostgreSQL
- **AI/ML**: OpenAI GPT-4（パーソナライゼーション）、TensorFlow（フォーム解析、栄養分析）、MediaPipe（ビデオ解析）
- **認証**: Clerk
- **決済**: Stripe（サブスクリプション管理）
- **インフラ**: Vercel（フロントエンド）、Railway（バックエンド）
- **ウェアラブル統合**: Apple HealthKit、Google Fit API、Fitbit API
- **モニタリング**: Sentry（エラートラッキング）、PostHog（アナリティクス）

**月額コスト見積もり:**

*初期フェーズ（2,000ユーザー想定）:*
- Vercel Pro: $20
- Railway Starter: $50（データベース + API）
- OpenAI API: $50（APIコール最適化、キャッシング活用で1ユーザーあたり$0.025想定）
- Stripe: $30（決済手数料）
- 合計: **約$150/月** → $250以下の制約内に収まる

*スケールフェーズ（1万ユーザー想定）:*
- Vercel Pro: $20
- Railway: $80（データベース + API + ビデオ処理）
- OpenAI API: $120（パーソナライゼーションコスト）
- Stripe: $120（決済手数料）
- 合計: **約$340/月** → 月間収益 $390,000（1万ユーザー × $39）に対して0.09%の低コスト率

**コスト最適化戦略:**
- OpenAI APIの使用量削減: ワークアウトプラン生成はキャッシング活用（同じ目標・体質のユーザーで再利用）
- フォームチェックの段階的展開: 初期は週1-2回のみAI分析、習慣化後は月1回に削減
- ビデオ処理の効率化: MediaPipeでローカル処理優先、クラウド処理は高度な分析のみ

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| **競合激化**: MyFitnessPal、Noom、Pelotonなど大手との競争 | 高 | 統合アプローチ（フィットネス + 栄養）、AI フォームチェック、手頃な価格で差別化 |
| **継続率の低さ**: フィットネスアプリは継続率が低い傾向（30日継続率 30-40%） | 高 | ゲーミフィケーション、コミュニティ機能、パーソナライズドリマインダーでエンゲージメント向上 |
| **AI 精度**: フォームチェックや栄養分析の精度が低いとユーザー離脱 | 中 | 人間トレーナーによるフィードバックループ、継続的なモデル改善 |
| **ウェアラブルAPI依存**: Apple、Googleなどのプラットフォーム変更リスク | 中 | 複数プラットフォーム対応、手動入力オプション提供 |
| **医療規制**: 健康アプリは医療機器として規制される可能性 | 中 | 免責事項を明確化、医師・栄養士との提携で信頼性担保 |

## データソース・調査方法

### 市場データ

- [Grand View Research - Fitness Apps Market](https://www.grandviewresearch.com/industry-analysis/fitness-app-market) — 信頼度: ★★★ — 取得日: 2026-02-16
- [Towards Healthcare - Fitness App Market Sizing](https://www.towardshealthcare.com/insights/fitness-app-market-sizing) — 信頼度: ★★★ — 取得日: 2026-02-16
- [DataM Intelligence - AI in Personalized Nutrition Market](https://www.prnewswire.com/news-releases/ai-in-personalized-nutrition-market-to-reach-usd-4-26-billion-by-2032--driven-by-predictive-analytics-deep-learning--real-time-dietary-intelligence--datam-intelligence-302617136.html) — 信頼度: ★★★ — 取得日: 2026-02-16
- [Towards Healthcare - Diet and Nutrition Apps Market](https://www.towardshealthcare.com/insights/diet-and-nutrition-apps-market-sizing) — 信頼度: ★★★ — 取得日: 2026-02-16

### 競合分析

- [Business of Apps - MyFitnessPal Statistics](https://www.businessofapps.com/data/myfitnesspal-statistics/) — 信頼度: ★★★ — 取得日: 2026-02-16
- [Pocketful of Joules - Noom vs MyFitnessPal](http://www.pocketfulofjoules.com/my-thoughts-on-noom-vs-myfitnesspal/) — 信頼度: ★★ — 取得日: 2026-02-16
- [Cal AI - Noom vs MyFitnessPal Comparison](https://www.calai.app/blog/noom-vs-myfitnesspal) — 信頼度: ★★ — 取得日: 2026-02-16
- [Fitia - Top Nutrition Apps with AI Coach](https://fitia.app/learn/article/top-nutrition-apps-ai-coach-2025/) — 信頼度: ★★ — 取得日: 2026-02-16

### トレンド情報

- [Robeco - Consumer Trends in 2026](https://www.robeco.com/en-int/insights/2026/02/consumer-trends-in-2026-safety-security-and-the-wearables-comeback) — 信頼度: ★★★ — 取得日: 2026-02-16
- [TATEEDA - Healthcare App Trends 2026](https://tateeda.com/blog/healthcare-mobile-apps-trends) — 信頼度: ★★ — 取得日: 2026-02-16

### 調査方法

**WebSearch クエリ:**
- "AI fitness wellness apps market size 2026 revenue"
- "AI-powered personalized nutrition apps market 2026"
- "personalized AI fitness nutrition coaching apps pricing features"
- "MyFitnessPal Noom fitness app revenue users pricing"

**WebFetch 確認:**
- Grand View Research の市場レポートで詳細なセグメント分析を確認
- Business of Apps で MyFitnessPal、Noom の収益・ユーザー数データを取得
- DataM Intelligence で AI 栄養市場の最新トレンドを確認
