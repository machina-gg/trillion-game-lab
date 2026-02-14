# Smart Game QA Automation Hub — 企画書

## ステータス

- 作成日: 2026-02-15
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

AI駆動のゲームQA自動化プラットフォームで、インディー開発者が月額$39で「人間QAテスター10名分」の網羅的テストを実現し、バグ検出率を従来の手動テストの3倍に向上させる。

## コンセプト

インディーゲーム開発者の60%はQA専任者を雇えず、ソロ開発者自身が手動テストを行うため、リリース後のバグ報告が多発し、レビュースコアが低下する。既存のゲームQAツール（GameDriver、Eggplant等）は大規模スタジオ向けで価格が$1,000+/月と高額。

本プロダクトは、**AI駆動のプレイパステスト + ビジュアルバグ検出 + クロスプラットフォーム自動化**を月額$39で提供し、インディー開発者が「ゼロ人件費でAAA級のQA品質」を実現できるプラットフォーム。

## 解決する課題

インディーゲーム開発者のQA課題:

1. **QA人件費の不足**: QAテスター1名の月給は$3,000-5,000だが、インディー予算では雇えない
1. **手動テストの限界**: ソロ開発者の手動テストはプレイパスが偏り、エッジケース（稀な操作パターン）を見逃す
1. **クロスプラットフォーム対応の困難**: Windows / macOS / Linux / モバイルの全環境で手動テストを行うのは現実的に不可能
1. **リリース後のバグ修正コスト**: Steam/Google Playでの低評価レビューは永続的なダメージとなり、売上に直結

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| ソロインディー開発者 | QA予算$0、手動テストのみ | テストカバレッジ30%未満、エッジケースを見逃す | 市場の60% |
| 小規模スタジオ（2-5名） | QA予算$500-2,000/月、外部QA委託検討 | 外部QA委託は高額（$50-100/時間）で継続困難 | 市場の20% |
| ゲームジャム参加者 | 48時間以内の開発・テスト | テスト時間がゼロに近く、バグだらけでリリース | 年間参加者推定50万人+ |

## 差別化ポイント

| 観点 | 既存プロダクト（GameDriver / Eggplant） | 当社プロダクト |
|------|-------------|-------------|
| 価格 | $1,000-5,000/月（エンタープライズ向け） | $39/月（インディー特化） |
| セットアップ時間 | 数日〜数週間（技術者必須） | 5分（SDKインポートのみ） |
| 対応プラットフォーム | Windows / macOS / iOS / Androidのみ | Unity / Unreal / Godot全対応、Web / Console含む |
| AI駆動テスト | 一部AIサポート | 完全AI駆動（プレイパス自動生成、ビジュアルバグ検出、パフォーマンス異常検知） |
| レポート | 技術レポート（開発者向け） | 非技術者向けダッシュボード + 動画付きバグレポート |
| ターゲット | 大規模スタジオ | ソロ〜小規模スタジオ |

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] **AI自動プレイテスト**: ゲーム状態をリアルタイム読み取り、数千の動的プレイパスを生成。エッジケース（稀な操作）を自動検出
- [ ] **ビジュアルバグ検出AI**: テクスチャの欠落、Z-fighting、UIオーバーラップ等をコンピュータビジョンで自動検出
- [ ] **クラッシュ・エラーログ自動収集**: 例外・クラッシュを自動検出し、スタックトレース + 再現動画を生成
- [ ] **Unity/Unreal/Godot SDK**: 各エンジン用の軽量SDKを提供（1行のコードでインポート完了）
- [ ] **バグレポートダッシュボード**: 検出バグを優先度順（Critical / High / Medium / Low）でソート。再現動画 + スクリーンショット付き

### Phase 2 以降

- [ ] **パフォーマンステスト**: FPS低下、メモリリーク、ロード時間異常を自動検出
- [ ] **アクセシビリティチェック**: 色覚異常対応、フォントサイズ、キーボード操作のみでのプレイ可否を自動検証
- [ ] **マルチプレイヤーテスト**: 複数AIエージェントによる同時接続テスト、ネットワーク遅延シミュレーション
- [ ] **回帰テスト**: コード変更後に既存機能が壊れていないか自動検証（CI/CD統合）
- [ ] **プレイヤー行動シミュレーション**: 実際のプレイヤー行動データを学習し、リアルなプレイパターンを再現

## ビジネスモデル

### 収益化戦略

1. **サブスクリプション収益**（主軸）
   - **Free**: $0/月 — 月間10テストまで、基本機能のみ
   - **Indie**: $39/月 — 月間100テスト、全MVP機能利用可
   - **Studio**: $149/月 — 月間500テスト、チーム機能（5ユーザー）、CI/CD統合
   - **Enterprise**: $499/月 — 無制限テスト、専用サポート、オンプレミス対応

1. **従量課金オプション**
   - 追加テストパック: $0.50/テスト（プランの上限超過時）

1. **アドオン収益**
   - パフォーマンステストアドオン: $19/月
   - アクセシビリティチェックアドオン: $19/月

### 収益予測（12ヶ月後）

- ターゲット: 月間1,500ユーザー（Free 800名、Indie 600名 × $39、Studio 90名 × $149、Enterprise 10名 × $499）
- 月間経常収益（MRR）: $42,300
- 年間経常収益（ARR）: $507,600

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（ゲーム開発市場全体） | $386.04B（2026年） | [Gaming Market Report](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) | 2026-02-15 |
| SAM（ゲームQA・テスト市場） | 推定$10-20B（開発コストの10-15%がQAに充当） | 推定（業界標準QA比率） | 2026-02-15 |
| SOM（インディー向けQA自動化ツール市場） | 推定$500M-1B（インディー開発者100万人 × 平均QA支出$500-1,000） | 推定 | 2026-02-15 |
| AI QAツールの効果 | バグ検出率が手動テストの3倍 | [AI-Powered Game Testing Aethir](https://ecosystem.aethir.com/blog-posts/ai-powered-game-testing-how-aethirs-decentralized-gpu-cloud-transforms-qa) | 2026-02-15 |
| 既存ツールの課題 | GameDriver / Eggplantは$1,000-5,000/月で高額 | [5 Game Testing Automation Tools](https://qawerk.com/blog/game-testing-automation-tools/) | 2026-02-15 |
| QAテスター人件費 | $3,000-5,000/月（1名） | [Game QA Testing Tools](https://reviewnprep.com/blog/what-are-the-best-qa-testing-tools-for-game-development/) | 2026-02-15 |

## 技術スタック（提案）

### フロントエンド

- Next.js 14（App Router）
- TypeScript（strict mode）
- Tailwind CSS
- Recharts（テスト結果ビジュアライゼーション）
- Shadcn/ui（UIコンポーネント）

### バックエンド

- Next.js API Routes
- Supabase（認証・データベース・ストレージ）
- Vercel Edge Functions（テスト結果処理）

### AI/ML

- OpenAI GPT-4 Vision API（ビジュアルバグ検出）— 月間推定$100
- Replicate API（画像分析）— 月間推定$50
- カスタムMLモデル（プレイパス生成）— TensorFlow.js（自己ホスト、コストゼロ）

### ゲームエンジンSDK

- Unity C# SDK
- Unreal C++ SDK
- Godot GDScript SDK

### クラウドテスト環境

- AWS EC2 Spot Instances（Windows / macOS / Linux仮想環境）— 月間推定$80（Spot Instanceで90%割引）

### インフラ

- Vercel（ホスティング）— $20/月（Pro Plan）
- Supabase（データベース + ストレージ）— $25/月（Pro Plan）
- Cloudflare R2（テスト動画ストレージ）— $15/月

### 月額コスト合計: 約$240-290

- Vercel: $20
- Supabase: $25
- Cloudflare R2: $15
- OpenAI GPT-4 Vision API: $100
- Replicate API: $50
- AWS EC2 Spot Instances: $30-80（使用量ベース）

→ **月額$250以下の制約に適合**（初期は$240で運用、スケール後に最適化）

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| AI誤検知（False Positive）の多発 | 高 | GPT-4 Visionのプロンプトを最適化し、誤検知率を10%以下に抑える。ユーザーフィードバックで継続学習 |
| ゲームエンジン仕様変更によるSDK互換性問題 | 中 | Unity / Unreal / Godotの各バージョンに対応したSDKを個別管理。メジャーアップデートは1週間以内に対応 |
| クラウドテスト環境コストの増加 | 中 | AWS Spot Instancesで90%コスト削減。テスト数が増加した場合は従量課金で追加料金を徴収 |
| 競合（GameDriver等）の価格引き下げ | 低 | インディー特化の「簡単セットアップ」で差別化。エンタープライズ向け競合は価格を下げにくい（既存顧客への影響） |
| テスト結果の信頼性問題 | 中 | バグレポートに再現動画 + スタックトレースを自動添付し、開発者が検証しやすい形式で提供。Critical/High/Medium/Lowの優先度自動分類 |

## データソース・調査方法

### 市場データ

- [Gaming Market Report 2026](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) — 信頼度: ★★★ — 取得日: 2026-02-15
- [Indie Game Development Cost Guide](https://www.juegostudio.com/blog/indie-game-development-cost) — 信頼度: ★★★ — 取得日: 2026-02-15

### 競合分析

- [5 Game Testing Automation Tools](https://qawerk.com/blog/game-testing-automation-tools/) — 信頼度: ★★★ — 取得日: 2026-02-15
- [What Are the Best QA Testing Tools](https://reviewnprep.com/blog/what-are-the-best-qa-testing-tools-for-game-development/) — 信頼度: ★★ — 取得日: 2026-02-15
- [AI Testing Tool QA Automation](https://qa.tech/) — 信頼度: ★★ — 取得日: 2026-02-15

### トレンド情報

- [AI-Powered Game Testing Aethir](https://ecosystem.aethir.com/blog-posts/ai-powered-game-testing-how-aethirs-decentralized-gpu-cloud-transforms-qa) — 信頼度: ★★★ — 取得日: 2026-02-15
- [How AI Transforms Game Testing](https://www.datacenters.com/news/from-bugs-to-brilliance-ai-s-impact-on-game-testing) — 信頼度: ★★ — 取得日: 2026-02-15
- [AI-Driven Automated Game Testing](https://www.ixiegaming.com/blog/ai-driven-automated-game-testing/) — 信頼度: ★★ — 取得日: 2026-02-15

### 調査方法

**WebSearchクエリ:**

- "game testing automation QA tools AI powered bug detection"
- "cloud gaming infrastructure cost AWS Azure game streaming"

**WebFetch確認サイト:**

- GameDriver公式サイト（価格・機能確認）
- Eggplant公式サイト（価格・機能確認）
- AWS EC2 Spot Instances公式ドキュメント（価格確認）
