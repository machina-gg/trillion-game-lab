# AI-Powered Game Asset Pipeline — 企画書

## ステータス

- 作成日: 2026-02-15
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

月額$49でインディーゲーム開発者に特化したAI資産生成パイプラインを提供し、従来60-80%のコスト削減を実現しながら、商用利用ライセンスを完全カバーする。

## コンセプト

インディーゲーム開発者の最大の課題は「限られた予算で高品質なアセットを大量生産する」こと。既存のAIツール（Leonardo AI: $10/月〜、Scenario: $15/月〜）は個別ツールとして優れているが、インディー開発者は複数ツールを組み合わせる必要があり、ワークフロー統合やライセンス管理が煩雑になる。

本プロダクトは、**アセット生成 + バッチ処理 + バージョン管理 + 商用ライセンス一元管理**を統合したオールインワンプラットフォームとして、ソロ開発者が月額$50以下で完結できるエコシステムを提供する。

## 解決する課題

インディーゲーム開発者が抱える3つの主要課題:

1. **予算制約**: ソロ開発者の典型的な予算は$10,000-$50,000で、アセット制作に割ける予算は限定的
2. **ツール乱立**: Leonardo AI、Scenario、Midjourney等の個別ツールを組み合わせる必要があり、学習コストと管理コストが高い
3. **ライセンス不安**: 生成アセットの商用利用ライセンスが曖昧なケースがあり、法的リスクを抱える

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| ソロインディー開発者 | 予算$10K-$50K、開発期間6-12ヶ月、2Dゲーム中心 | アセット制作が開発期間の30-40%を占める | 60%がセルフファンド |
| 小規模スタジオ（2-5名） | 予算$50K-$200K、3Dゲーム対応 | 複数ツールの管理・ライセンス統合が煩雑 | 市場の約20% |
| ゲームジャム参加者 | 48時間以内の高速プロトタイピング | アセット生成速度が勝負を分ける | 年間参加者数推定50万人+ |

## 差別化ポイント

| 観点 | 既存プロダクト（Leonardo AI / Scenario） | 当社プロダクト |
|------|-------------|-------------|
| 提供範囲 | 単一機能（画像生成のみ） | アセット生成 + Git統合 + ライセンス管理 + バッチ処理 |
| 価格 | Leonardo $10/月、Scenario $15/月（別々に契約） | $49/月で全機能統合 |
| ワークフロー統合 | なし（手動でUnity/Unreal等にインポート） | Unity/Unreal/Godotへの自動エクスポート |
| ライセンス管理 | 各ツールで個別確認が必要 | 生成アセット全てに自動で商用ライセンス証明書を発行 |
| バージョン管理 | なし | Git連携でアセット履歴を自動追跡 |
| ターゲット | 汎用的なクリエイター | ゲーム開発者に特化（スプライトシート、タイルセット等の専用フォーマット対応） |

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] **AI画像生成エンジン**: 2D/3Dアセット生成（キャラクター、背景、UI要素）。APIはStable Diffusion XL + LoRAカスタムモデル
- [ ] **ゲームエンジン自動統合**: Unity/Unreal/Godotへの1クリックエクスポート（スプライトシート、タイルマップ形式対応）
- [ ] **バッチ処理**: 複数アセットの一括生成（例: キャラクタースプライト8方向 × 4アニメーション状態を1コマンドで生成）
- [ ] **商用ライセンス証明書**: 生成アセットごとに自動発行。CC0相当のライセンスを保証
- [ ] **Gitワークフロー統合**: 生成アセットをGitリポジトリに自動コミット、バージョン履歴管理

### Phase 2 以降

- [ ] **カスタムモデルトレーニング**: ユーザー独自のアートスタイルでLoRAモデルをファインチューン
- [ ] **音声アセット生成**: BGM、SE、ボイスオーバーの生成（ElevenLabs API統合）
- [ ] **3Dモデル生成**: テクスチャ付き3Dメッシュの生成（GLB/FBX形式）
- [ ] **コミュニティマーケットプレイス**: 生成アセットの販売・購入プラットフォーム
- [ ] **AI QA統合**: 生成アセットの品質チェック（サイズ、フォーマット、互換性の自動検証）

## ビジネスモデル

### 収益化戦略

1. **サブスクリプション収益**（主軸）
   - **Starter**: $19/月 — 月間500アセット生成、基本機能のみ
   - **Pro**: $49/月 — 月間2,000アセット生成、全機能利用可、優先サポート
   - **Studio**: $149/月 — 無制限生成、チーム機能（5ユーザーまで）、カスタムモデルトレーニング

2. **アドオン収益**
   - カスタムLoRAモデルトレーニング: $29/モデル
   - 音声アセットパック: $9.99/パック

3. **フリーミアム戦略**
   - 無料プラン: 月間50アセット生成、透かし付き、コミュニティサポートのみ

### 収益予測（12ヶ月後）

- ターゲット: 月間1,000ユーザー（Starter 600名 × $19 + Pro 350名 × $49 + Studio 50名 × $149）
- 月間経常収益（MRR）: $36,040
- 年間経常収益（ARR）: $432,480

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（ゲーム開発市場全体） | $386.04B（2026年） | [Gaming Market Report](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) | 2026-02-15 |
| SAM（インディーゲーム開発者向けツール市場） | 推定$5-10B（ゲーム開発市場の1-2%） | 推定（ソロ開発者60%がセルフファンド） | 2026-02-15 |
| SOM（AI資産生成ツール市場） | $650M（2030年予測、生成AIゲーム市場、CAGR 48.2%） | [CG研究所 生成AIゲーム制作記事](https://cg-kenkyujo.com/seiseiai-game/) | 2026-02-15 |
| CAGR（AI生成ツール市場） | 48.2% | [AI Gaming記事](https://www.ai-gaming.jp/ai-game-future/) | 2026-02-15 |
| インディー開発者の予算 | $10,000-$50,000（ソロ開発者） | [Indie Game Development Cost Guide](https://www.juegostudio.com/blog/indie-game-development-cost) | 2026-02-15 |
| AI導入によるコスト削減 | 60-80% | [Best AI Tools for Mass Producing Game Assets](https://apatero.com/blog/best-ai-tools-mass-produce-commercial-game-assets-2025) | 2026-02-15 |

## 技術スタック（提案）

### フロントエンド
- Next.js 14（App Router）
- TypeScript（strict mode）
- Tailwind CSS
- Shadcn/ui（UIコンポーネント）

### バックエンド
- Next.js API Routes
- Vercel Edge Functions（画像最適化処理）
- Supabase（認証・データベース・ストレージ）

### AI/ML
- Replicate API（Stable Diffusion XL + LoRA）— $0.0055/秒（月間2,000アセット生成で推定$50-100）
- OpenAI GPT-4 API（プロンプト最適化）— 月間推定$20

### インフラ
- Vercel（ホスティング）— $20/月（Pro Plan）
- Supabase（データベース + ストレージ）— $25/月（Pro Plan、50GBストレージ）
- Cloudflare R2（アセットストレージ）— $15/月（1TB、$0.015/GB）

### 月額コスト合計: 約$130-180
- Vercel: $20
- Supabase: $25
- Cloudflare R2: $15
- Replicate API: $50-100（使用量ベース）
- OpenAI API: $20

→ **月額$250以下の制約に適合**

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| AI生成ライセンス問題 | 高 | Replicate APIの利用規約を精査し、商用利用が明示的に許可されているモデルのみ使用。生成アセットにCC0ライセンスを付与し、法的リスクを最小化 |
| 競合（Leonardo AI、Scenario）の価格競争 | 中 | 単一機能ではなく「統合ワークフロー」で差別化。ゲーム開発者特化の機能（スプライトシート、Git連携）で参入障壁を構築 |
| API料金の高騰 | 中 | Replicate APIの代替としてオープンソースのStable Diffusionを自己ホストする選択肢を用意（コスト削減）。初期はAPIを使用し、スケール後に移行 |
| ユーザー獲得コスト（CAC）の増加 | 中 | コンテンツマーケティング（ゲームジャム向けチュートリアル、YouTube解説動画）とSEO最適化でオーガニック流入を最大化。有料広告は最小限に抑える |
| 品質のばらつき | 中 | AI生成結果のフィードバックループを導入し、低品質な出力を自動検出・再生成する仕組みを構築 |

## データソース・調査方法

### 市場データ

- [Gaming Market Report 2026](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) — 信頼度: ★★★ — 取得日: 2026-02-15
- [Mordor Intelligence Video Game Market](https://www.mordorintelligence.com/industry-reports/video-game-market) — 信頼度: ★★★ — 取得日: 2026-02-15
- [Indie Game Development Cost Guide](https://www.juegostudio.com/blog/indie-game-development-cost) — 信頼度: ★★★ — 取得日: 2026-02-15

### 競合分析

- [Leonardo AI vs Scenario Comparison](https://pointofai.com/compare/leonardo-ai-vs-scenario) — 信頼度: ★★★ — 取得日: 2026-02-15
- [Best AI Tools for Mass Producing Game Assets](https://apatero.com/blog/best-ai-tools-mass-produce-commercial-game-assets-2025) — 信頼度: ★★★ — 取得日: 2026-02-15
- [Leonardo AI Review 2025](https://www.aimodelsrank.com/reviews/leonardo-ai) — 信頼度: ★★ — 取得日: 2026-02-15

### トレンド情報

- [Gaming Trends 2026](https://www.blog.udonis.co/mobile-marketing/mobile-games/gaming-trends) — 信頼度: ★★★ — 取得日: 2026-02-15
- [CG研究所 生成AIゲーム制作記事](https://cg-kenkyujo.com/seiseiai-game/) — 信頼度: ★★ — 取得日: 2026-02-15
- [AI Game Development Tools 2026](https://www.elsner.com/ai-game-development-tools/) — 信頼度: ★★ — 取得日: 2026-02-15

### 調査方法

**WebSearchクエリ:**
- "game industry trends 2026 AI UGC cloud gaming market"
- "AI game asset generation tools competitors pricing Scenario Leonardo"
- "indie game developer tools budget constraints solo developer 2026"

**WebFetch確認サイト:**
- Leonardo AI公式サイト（価格・機能確認）
- Scenario公式サイト（価格・機能確認）
- Replicate API公式ドキュメント（価格・利用規約確認）
