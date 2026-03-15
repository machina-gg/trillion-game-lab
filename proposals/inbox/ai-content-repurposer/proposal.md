# AI コンテンツリパーパサー — 企画書

## ステータス

- 作成日: 2026-03-15
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

ブログ記事や動画トランスクリプトを 1 つ貼り付けるだけで、ツイート 10 本・LinkedIn 投稿 5 本・ニュースレター・動画スクリプトを数秒で自動生成する AI Micro SaaS。コンテンツクリエイターが「1 つ作って全プラットフォームに展開する」時間を 90% 削減する。

## コンセプト

コンテンツ制作の最大のボトルネックは「作成」ではなく「展開」にある。1 本のブログ記事を Twitter 向け・LinkedIn 向け・メルマガ向けに書き直すには、それぞれのプラットフォーム文化・文字数・トーンを理解した上で数時間かかる。

本プロダクトは、ユーザーが元コンテンツを貼り付けるだけで、各プラットフォームのベストプラクティスに沿った複数フォーマットのコンテンツを即時生成する。単なる「要約 + 短縮」ではなく、プラットフォームごとのエンゲージメントパターンを学習した最適化済みコンテンツを出力する点が差別化の核心。

## 解決する課題

コンテンツクリエイター・マーケターが直面する 3 つの課題:

1. **時間コスト**: 1 つのブログ記事を 5 プラットフォーム向けに展開するのに平均 3〜5 時間かかる
2. **プラットフォーム最適化の難しさ**: Twitter のフック文、LinkedIn のストーリーテリング、メルマガの CTA はそれぞれ異なるスキルが必要
3. **コンテンツ量不足**: ソーシャルメディアのアルゴリズムは高頻度投稿を優遇するが、質を保ちながら量を出すことが困難

65% のクリエイターが「信頼できるコンテンツワークフローがない」と回答し、42% が「コンテンツの効率的な再活用に苦労している」と答えている（2025 年調査）。

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| ソロクリエイター | YouTuber・Podcastar・ブロガー。37% が一人で活動 | 複数プラットフォーム対応の時間不足 | 全世界 200M+ 人 |
| コンテンツマーケター | 企業のマーケ担当。週複数本の記事・SNS 投稿が必要 | 1 人で複数チャネルを担当、リソース不足 | 米国だけで約 45M 人のプロクリエイター |
| スタートアップ創業者 | プロダクト情報を複数 SNS で発信したい | コンテンツ制作スキルと時間の両方が不足 | グローバルスタートアップ数百万社 |

## 差別化ポイント

| 観点 | Repurpose.io | Castmagic | Lately.ai | 当社プロダクト |
|------|-------------|-----------|-----------|-------------|
| 主な入力形式 | 動画・音声 | 音声・動画 | テキスト・音声 | テキスト・URL・動画トランスクリプト |
| 出力フォーマット | 動画クリップ | SNS 投稿・ブログ | SNS 投稿のみ | ツイート・LinkedIn・メルマガ・動画スクリプト |
| プラットフォーム最適化 | なし | 基本的 | AI 学習あり | プラットフォーム別トーン最適化 |
| 価格（月額） | $29〜 | $21〜 | $99〜 | $19〜（想定） |
| ブランドボイス学習 | なし | なし | あり（高額プラン） | 全プランで提供 |
| 一括生成本数 | なし | なし | なし | 1 入力 → 20+ 出力 |

**競合が対応していない Gap**:

- Repurpose.io と Castmagic は動画・音声特化で、テキスト入力からの多フォーマット展開が弱い
- Lately.ai は $99〜と高額で、ソロクリエイターに手が届かない
- 全競合とも「1 入力 → 20+ 出力を一括生成」する UX を提供していない

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] **コンテンツ入力**: テキスト貼り付け・URL（ブログ記事）・動画 URL（YouTube）をサポート
- [ ] **マルチフォーマット生成**: ツイートスレッド（10 本）・LinkedIn 投稿（3〜5 本）・メルマガ本文・動画スクリプトを一括生成
- [ ] **プラットフォーム別最適化**: 各 SNS のトーン・文字数・ハッシュタグ戦略に自動適応
- [ ] **ワンクリックコピー**: 生成コンテンツを個別にコピー・編集できる UI
- [ ] **ブランドボイス設定**: サンプルテキストを登録してトーンを学習させる機能

### Phase 2 以降

- [ ] **直接投稿連携**: Buffer / Hootsuite API 連携で生成コンテンツを直接スケジュール投稿
- [ ] **パフォーマンス分析**: どのフォーマットが高エンゲージメントかフィードバック学習
- [ ] **チーム機能**: 複数メンバーでブランドボイスを共有・管理
- [ ] **テンプレート保存**: よく使う生成パターンをテンプレート化
- [ ] **多言語対応**: 日本語・英語・スペイン語など主要言語間の翻訳リパーパス

## ビジネスモデル

**フリーミアム + サブスクリプション**

| プラン | 月額 | 内容 |
|--------|------|------|
| Free | $0 | 月 5 回生成・基本フォーマット（ツイート・LinkedIn のみ） |
| Starter | $19 | 月 50 回生成・全フォーマット・ブランドボイス 1 件 |
| Pro | $49 | 無制限生成・ブランドボイス 5 件・優先サポート |
| Team | $99 | 無制限生成・ブランドボイス 20 件・3 ユーザー |

**収益予測（12 ヶ月目）**:

- 無料ユーザー: 2,000 人（有料転換率 5%）
- 有料ユーザー: 100 人（平均 ARPU $35）
- 月次収益: $3,500 MRR → ARR $42,000

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（生成 AI コンテンツ作成市場） | $14.84B（2024）→ $80.12B（2030） | [Grand View Research](https://www.grandviewresearch.com/industry-analysis/generative-ai-content-creation-market-report) | 2026-03-15 |
| CAGR | 32.5%（2025-2030） | [Grand View Research](https://www.grandviewresearch.com/industry-analysis/generative-ai-content-creation-market-report) | 2026-03-15 |
| SAM（AI コンテンツリパーパシングツール市場） | $1.8B（2025）→ $2.3B（2026） | [Intel Market Research](https://www.intelmarketresearch.com/ai-content-creationoptimization-software-market-37066) | 2026-03-15 |
| SOM（ソロクリエイター・中小企業向け Micro SaaS） | $90M（SAM の 5% 推定） | 推定 | 2026-03-15 |
| クリエイターエコノミー規模 | 200M+ 人のアクティブクリエイター | [Scrumball](https://www.scrumball.com/blog/how-many-content-creators-worldwide) | 2026-03-15 |

## 技術スタック（提案）

月額 $250 以下の制約に適合した構成:

| カテゴリ | 技術 | 月額コスト |
|---------|------|-----------|
| フロントエンド | Next.js 14 + TypeScript + Tailwind CSS | $0 |
| バックエンド | Next.js API Routes（サーバーレス） | $0 |
| ホスティング | Vercel（Hobby → Pro） | $0〜$20 |
| AI | OpenAI GPT-4o-mini API | $50〜$100（従量課金） |
| DB | Supabase（Postgres + Auth） | $0〜$25 |
| キャッシュ | Vercel KV（Redis） | $0〜$20 |
| 決済 | Stripe | 売上の 2.9% + 手数料 |
| **合計** | | **$70〜$165/月** |

**コスト最適化のポイント**:

- GPT-4o-mini は GPT-4 比で 15 倍安く、コンテンツ生成タスクの品質は十分
- プロンプトキャッシュで同一入力の再計算を防ぎ API コストを 50% 削減
- Supabase の無料枠（500MB DB・50K MAU）で初期フェーズはほぼ無料

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| AI 生成コンテンツの品質がユーザー期待を下回る | 高 | 複数プロンプト戦略 + ユーザーフィードバックループで継続改善 |
| OpenAI API 価格上昇 | 中 | Anthropic Claude / Google Gemini のマルチベンダー対応で依存度分散 |
| 大手（Buffer・Hootsuite）が類似機能を内包 | 高 | ブランドボイス学習の深さ・生成速度・UX のシンプルさで差別化 |
| コンテンツ著作権・AI 生成物の法的問題 | 中 | 利用規約で「入力コンテンツは自社所有」を明確化。生成物の著作権はユーザーに帰属 |
| 類似プロダクトの乱立（競合増加） | 中 | 特定ニッチ（日本語クリエイター向け）に特化しローカル市場でポジション確立 |

## データソース・調査方法

### 市場データ

- [Grand View Research: Generative AI Content Creation Market](https://www.grandviewresearch.com/industry-analysis/generative-ai-content-creation-market-report) — 信頼度: ★★★ — 取得日: 2026-03-15
- [Intel Market Research: AI Content Creation Optimization Software Market](https://www.intelmarketresearch.com/ai-content-creationoptimization-software-market-37066) — 信頼度: ★★ — 取得日: 2026-03-15
- [Scrumball: Global Demographics of Content Creators](https://www.scrumball.com/blog/how-many-content-creators-worldwide) — 信頼度: ★★ — 取得日: 2026-03-15

### 競合分析

- [Repurpose.io 公式サイト](https://repurpose.io/) — 信頼度: ★★★ — 取得日: 2026-03-15
- [Repurpose.io 料金ページ](https://repurpose.io/pricing/) — 信頼度: ★★★ — 取得日: 2026-03-15
- [Castmagic 料金ページ](https://www.castmagic.io/pricing) — 信頼度: ★★★ — 取得日: 2026-03-15
- [Lately.ai 料金ページ](https://www.lately.ai/pricing/lately-pricing) — 信頼度: ★★★ — 取得日: 2026-03-15

### トレンド情報

- [Spiralytics: 2025 Content Creator Economy Statistics](https://www.spiralytics.com/blog/content-creator-statistics-2025/) — 信頼度: ★★ — 取得日: 2026-03-15
- [Netguru: AI Content Repurposing Top Tools 2025](https://www.netguru.com/blog/ai-content-repurposing-top-tools-and-success-stories) — 信頼度: ★★ — 取得日: 2026-03-15

### 調査方法

- WebSearch クエリ: "AI content repurposing tools market size 2025 2026"
- WebSearch クエリ: "content repurposing SaaS competitors Repurpose.io Lately.ai pricing features 2025"
- WebSearch クエリ: "content creator pain points repurposing content multiple platforms survey 2025"
- WebSearch クエリ: "Castmagic MagicShots ContentFries AI content repurposing pricing comparison 2025"
- WebFetch: Castmagic 料金ページ（公式）
- WebFetch: Grand View Research 市場レポート（公式）
