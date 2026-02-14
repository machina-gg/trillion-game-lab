# Indie Launch Intelligence — 企画書

## ステータス

- 作成日: 2026-02-15
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

Steamウィッシュリスト最適化とローンチ戦略をAI駆動で自動化し、インディー開発者が月額$29でウィッシュリスト転換率18%→25%+への向上を実現するオールインワンプラットフォーム。

## コンセプト

インディーゲームの成功は「ローンチ前のウィッシュリスト獲得数」で80%決まる。Steamでは10,000ウィッシュリストで初週1,800本販売（転換率18%）が期待値だが、多くのインディー開発者はマーケティング予算が限られており、効果的な施策を打てない。

本プロダクトは、**Steam API連携 + AI分析 + 無料マーケティング施策の自動化**により、広告費ゼロでウィッシュリスト獲得を最大化する「インディー特化のローンチインテリジェンスプラットフォーム」を提供する。

## 解決する課題

インディーゲーム開発者のマーケティング課題:

1. **予算不足**: マーケティング予算$0-5,000が大半で、広告を打てない
1. **情報の分散**: Steam Analytics、Reddit、Twitter、Discord等のデータが分散しており、統合分析ができない
1. **ベストプラクティスの不明確さ**: 「いつ、何を、どこで発信すべきか」の科学的根拠がない
1. **ウィッシュリスト獲得の難しさ**: 平均的なインディーゲームは初週500-2,000ウィッシュリストしか獲得できず、ローンチ失敗のリスクが高い

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| ソロインディー開発者 | マーケティング予算$0-1,000、初回リリース | マーケティング知識ゼロ、時間がない | 市場の60% |
| 小規模スタジオ（2-5名） | マーケティング予算$1,000-5,000、複数タイトル運用 | データ分析リソース不足、広告ROIが不明 | 市場の20% |
| ゲームパブリッシャー（インディー支援） | 複数タイトルを同時管理 | 各タイトルのパフォーマンス比較・最適化が手動で煩雑 | 市場の10% |

## 差別化ポイント

| 観点 | 既存プロダクト（Steam Analytics / VG Insights） | 当社プロダクト |
|------|-------------|-------------|
| データ範囲 | Steamデータのみ | Steam + Reddit + Twitter/X + Discord統合分析 |
| 価格 | VG Insights Pro: $30/月 | $29/月で全機能 + AI施策自動化 |
| 施策実行 | データ閲覧のみ（施策は手動） | AI施策自動生成 + 投稿スケジューリング + A/Bテスト自動実施 |
| ウィッシュリスト予測 | なし | AIによるローンチ日別ウィッシュリスト予測（90%精度） |
| 競合分析 | 手動で類似ゲームを検索 | AIが類似タグ・ジャンルから競合を自動特定、ベンチマーク比較 |
| 無料施策最適化 | なし | Reddit投稿、ゲームフェス参加、Steam Eventの最適タイミングをAI推奨 |

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] **Steam API統合**: ウィッシュリスト数、フォロワー数、トラフィックソースをリアルタイム取得・ダッシュボード表示
- [ ] **AI競合分析**: Steam Tags Queryを自動化し、類似ゲームTop 20を抽出。価格、リリース日、ウィッシュリスト数をベンチマーク比較
- [ ] **ウィッシュリスト予測AI**: 現在のトレンドから「ローンチ時のウィッシュリスト総数」を予測（誤差±10%）
- [ ] **無料施策カレンダー**: Steam公式フェスティバル、主要ゲームジャム、Reddit r/gamedevの投稿最適日をカレンダー表示
- [ ] **AI投稿文生成**: Reddit / Twitter / Discord用の投稿文をGPT-4で自動生成（A/Bテスト用に3バリエーション）

### Phase 2 以降

- [ ] **自動投稿スケジューリング**: Reddit / Twitter / Discordへの自動投稿（時間帯最適化）
- [ ] **インフルエンサーマッチング**: YouTuber / Twitchストリーマーとのマッチング（予算・ジャンル適合度スコアリング）
- [ ] **ローンチ日最適化AI**: 競合リリーススケジュールを分析し、最適なローンチ日を提案
- [ ] **ウィッシュリストCRM**: ウィッシュリスト追加ユーザーのデモグラフィックを分析し、セグメント別メッセージング
- [ ] **プレスキット自動生成**: Screenshots、動画、プレスリリースを自動フォーマット（Press Kitty連携）

## ビジネスモデル

### 収益化戦略

1. **サブスクリプション収益**（主軸）
   - **Free**: $0/月 — Steam Analytics閲覧のみ、広告表示あり
   - **Indie**: $29/月 — 全機能利用可、1タイトル、AI投稿文生成月間30回
   - **Studio**: $99/月 — 全機能、5タイトルまで、自動投稿機能、優先サポート
   - **Publisher**: $299/月 — 無制限タイトル、チーム機能（10ユーザー）、ホワイトラベル対応

1. **アドオン収益**
   - インフルエンサー紹介手数料: マッチング成立時に10%の仲介手数料
   - プレミアムレポート: 競合分析詳細レポート $49/レポート

1. **アフィリエイト収益**
   - Steam Events、ゲームフェス参加費のアフィリエイト（参加促進で5-10%手数料）

### 収益予測（12ヶ月後）

- ターゲット: 月間2,000ユーザー（Free 1,200名、Indie 700名 × $29、Studio 90名 × $99、Publisher 10名 × $299）
- 月間経常収益（MRR）: $32,210
- 年間経常収益（ARR）: $386,520

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（ゲーム開発市場全体） | $386.04B（2026年） | [Gaming Market Report](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) | 2026-02-15 |
| SAM（インディーゲーム開発者向けマーケティングツール市場） | 推定$2-5B（TAMの0.5-1%） | 推定（インディー開発者数100万人 × 平均マーケティング予算$2,000-5,000） | 2026-02-15 |
| SOM（Steam特化マーケティングツール市場） | 推定$100-300M（年間Steam新規リリース数14,000タイトル × 平均支出$7,000-20,000） | 推定（Steam年間リリース数ベース） | 2026-02-15 |
| Steamウィッシュリスト転換率 | 18%（中央値、初週） | [Visibility and Wishlist Masterclass](https://www.progamemarketing.com/p/visibility-and-wishlist-masterclass) | 2026-02-15 |
| ウィッシュリスト10,000件のインパクト | Popular Upcomingエリア表示（追加ウィッシュリスト獲得） | [How to Gain Wishlists](https://fungies.io/how-to-gain-wishlists-for-your-indie-game/) | 2026-02-15 |
| 無料マーケティングツールの効果 | Reddit月間20万PV、Steam Events $100で2,800ウィッシュリスト（CPL $0.04） | [Indie Survival Guide](https://opgamemarketing.substack.com/p/the-indie-survival-guide-to-game) | 2026-02-15 |

## 技術スタック（提案）

### フロントエンド

- Next.js 14（App Router）
- TypeScript（strict mode）
- Tailwind CSS
- Recharts（データビジュアライゼーション）
- Shadcn/ui（UIコンポーネント）

### バックエンド

- Next.js API Routes
- Supabase（認証・データベース）
- Vercel Edge Functions（Steam API Proxy）

### データ収集・分析

- Steam API（公式APIでウィッシュリスト・フォロワー数取得）
- Reddit API（投稿パフォーマンス分析）
- Twitter/X API（エンゲージメント分析）
- OpenAI GPT-4 API（投稿文生成・競合分析）— 月間推定$50

### インフラ

- Vercel（ホスティング）— $20/月（Pro Plan）
- Supabase（データベース + 認証）— $25/月（Pro Plan）
- Upstash Redis（キャッシュ）— $10/月

### 月額コスト合計: 約$105

- Vercel: $20
- Supabase: $25
- Upstash Redis: $10
- OpenAI API: $50（使用量ベース）

→ **月額$250以下の制約に適合**

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| Steam API利用制限・規約変更 | 高 | Steam公式APIを使用し、利用規約を遵守。非公式スクレイピングは一切行わない。代替データソースとしてSteamDB APIを検討 |
| 競合（VG Insights）の価格競争 | 中 | データ閲覧だけでなく「施策実行の自動化」で差別化。無料プランでユーザーを獲得し、有料転換を促進 |
| AIによる投稿文の品質問題 | 中 | GPT-4のプロンプトを最適化し、インディーゲームマーケティングの専門知識を事前学習。ユーザーフィードバックループで継続改善 |
| Reddit / Twitter API費用の増加 | 中 | Reddit / Twitter APIの無料枠を活用。有料化した場合は、ユーザーが自身のAPIキーを設定できるオプションを提供 |
| ウィッシュリスト予測の精度問題 | 中 | 過去のローンチデータ（Steam公開データ）を機械学習モデルで学習。予測誤差±10%を目標とし、精度が低い場合は予測範囲を広げる |

## データソース・調査方法

### 市場データ

- [Gaming Market Report 2026](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) — 信頼度: ★★★ — 取得日: 2026-02-15
- [Indie Game Development Cost Guide](https://www.juegostudio.com/blog/indie-game-development-cost) — 信頼度: ★★★ — 取得日: 2026-02-15

### 競合分析

- VG Insights公式サイト（価格・機能確認）— 信頼度: ★★★ — 取得日: 2026-02-15
- Steam公式ドキュメント（API仕様確認）— 信頼度: ★★★ — 取得日: 2026-02-15

### トレンド情報

- [Visibility and Wishlist Masterclass](https://www.progamemarketing.com/p/visibility-and-wishlist-masterclass) — 信頼度: ★★★ — 取得日: 2026-02-15
- [How to Promote Indie Game Low Budget](https://retrostylegames.com/blog/how-to-promote-an-indie-game-with-a-low-budget/) — 信頼度: ★★★ — 取得日: 2026-02-15
- [Indie Survival Guide to Game Marketing](https://opgamemarketing.substack.com/p/the-indie-survival-guide-to-game) — 信頼度: ★★★ — 取得日: 2026-02-15
- [How to Gain Wishlists](https://fungies.io/how-to-gain-wishlists-for-your-indie-game/) — 信頼度: ★★ — 取得日: 2026-02-15

### 調査方法

**WebSearchクエリ:**

- "indie game marketing budget free tools visibility Steam wishlist"
- "game streaming platform market size revenue 2026"

**WebFetch確認サイト:**

- Steam公式ドキュメント（API仕様・利用規約確認）
- VG Insights公式サイト（価格・機能確認）
- Reddit r/gamedev（インディー開発者のマーケティング課題調査）
