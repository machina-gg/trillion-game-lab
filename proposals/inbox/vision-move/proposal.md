# vision-move — 企画書

## ステータス

- 作成日: 2026-03-15
- 作成者: Planner
- ステータス: draft

## エレベーターピッチ

リモートワーカーの身体的健康を守る Chrome 拡張。姿勢リマインダー・目のケア・ストレッチガイドをブラウザに統合し、作業を止めずに筋骨格系の不調を予防する。

## コンセプト

vision-move は、Chrome ブラウザ上で作業中のリモートワーカーに対し、科学的根拠に基づいた休憩・姿勢・目のケアをリアルタイムで提供する健康コーチ拡張機能。

既存の集中力ツール（vision-focus）は「仕事に集中させる」ことに特化しているが、長時間集中した結果として生じる身体的ダメージには対処していない。vision-move は Vision シリーズの補完製品として、**「集中 × 健康」の両立**を実現する。

## 解決する課題

リモートワーカーの 61% が筋骨格系の痛みを経験する（出典: [PMC研究 PMC9800234](https://pmc.ncbi.nlm.nih.gov/articles/PMC9800234/)、2026-03-15 取得）。部位別では首 60.3%・腰 59.5%・肩 49.6%・上背部 42.1%・手首/手 35.5% が最も高い有症率を示し、複数部位に同時に痛みを抱えるケースが多い（同出典）。

主な課題:

- **姿勢の悪化**: 非人間工学的なデスク環境での長時間作業
- **眼精疲労**: 20-20-20 ルール（20 分ごとに 6m 先を 20 秒見る）の実践を忘れる
- **休憩の省略**: 集中しすぎて体が固まっても気づかない
- **断片化ツール問題**: 姿勢・眼・休憩の各ツールがバラバラで管理が煩雑

## ターゲットユーザー

| セグメント | 特徴 | ペインポイント | 規模 |
|-----------|------|-------------|------|
| フルリモートワーカー | 1日8時間以上 PC 作業、自宅環境 | 姿勢が悪化しやすい非エルゴノミクス環境 | 米国 3,600 万人（2025 年）|
| ハイブリッドワーカー | オフィス+在宅を週3以上切り替え | デスク環境が日々変わり姿勢が安定しない | グローバル 42% の労働力 |
| フリーランス・クリエイター | デザイナー・エンジニア・ライター | 長時間集中作業後の身体的ダメージを放置しがち | グローバル約 1.5 億人 |

## 競合詳細分析

### PostureMinder

- **ユーザー数**: 20,000+（[Chrome Web Store](https://chromewebstore.google.com/detail/postureminder/dkmkfopiihabelocpelofchappjjnpkm)、2026-03-15 取得）
- **評価**: 4.48 / 5（123件）
- **価格**: 無料
- **主な機能**: カスタマイズ可能なリマインド間隔、スマートハイド（離席検知）、ウォークリマインダー、ユーモラスなメッセージ
- **弱点**:
  - 通知ズレ・通知未表示の問題が継続報告。公式 FAQ によると「システムクロックの遅延やその他の処理遅延により、リマインダーが表示されないことがある」と明記（[PostureMinder FAQ](https://postureminder.app/faq?c=1)、2026-03-15 取得）
  - 通知音は出るが視覚的なポップアップが出ない不具合がレビューで複数報告（[Chrome Web Store サポートページ](https://chromewebstore.google.com/detail/postureminder/dkmkfopiihabelocpelofchappjjnpkm/support)、2026-03-15 取得）
  - 姿勢リマインドのみで目のケア機能なし

### RiseLoop（Stand Up Timer & Break Reminder）

- **ユーザー数**: 非公開（少数）
- **評価**: 非公開
- **価格**: 無料
- **主な機能**: スタンドアップタイマー、Pomodoro 連携、ミニマルUI、オフライン動作、データ収集なし
- **弱点**:
  - 機能が「立ち上がりリマインド」のみに特化しており、目のケア・ストレッチガイドが未搭載
  - カスタマイズ項目が限定的
  - ユーザー数・評価データが非公開で市場トラクション不明（[Chrome Web Store](https://chromewebstore.google.com/detail/riseloop-stand-up-timer-b/hhobmbfggpimmmbkgjobngkombglobkm)、2026-03-15 取得）

### eyeCare — Protect your vision

- **ユーザー数**: 50,000+（[chrome-stats.com](https://chrome-stats.com/d/pgmnenagoehciiknchfbobbcjdmnmhab)、2026-03-15 取得）
- **評価**: 4.29 / 5（256件）
- **価格**: 無料
- **主な機能**: 20-20-20 ルールリマインダー、カスタマイズ可能な通知、サウンドアラート、デバイス間設定同期、腰ストレッチ案内
- **弱点**:
  - 目のケアが中心で、姿勢リマインドとの統合が弱い
  - カスタムサウンドや音量調整が未対応（ユーザーレビューで要望多数）
  - Manifest V3 への移行状況が不明確

## 差別化ポイント

| 観点 | PostureMinder | RiseLoop | eyeCare | vision-move |
|------|-------------|-------------|-------------|-------------|
| 機能統合 | 姿勢のみ | 立ち上がりのみ | 目のみ（腰ストレッチ少し） | 姿勢・目・ストレッチを1つに統合 |
| パーソナライズ | カスタム間隔あり | 限定的 | カスタム間隔あり | 作業負荷・時間帯・疲労度に応じて間隔を自動調整 |
| ガイド品質 | テキスト通知のみ | テキスト通知のみ | テキスト通知のみ | アニメーション付きビジュアルストレッチガイド |
| Vision シリーズ連携 | なし | なし | なし | vision-focus と連携し集中セッション後に自動ブレーク提案 |
| プライバシー | ローカル処理 | ローカル処理（明示） | デバイス間同期あり | ローカル処理のみ、データ外部送信なし |
| 信頼性 | 通知ズレ問題が継続報告 | 情報不足 | 比較的安定 | MV3 対応で確実な通知設計 |
| ユーザー数 | 20,000+ | 非公開 | 50,000+ | — |

## 機能一覧

### MVP（最小実行可能プロダクト）

- [ ] 機能1 — **エルゴノミクスタイマー**: 作業 30 分ごとに姿勢チェック・立ち上がり・目のケアをリマインド。間隔はユーザーが 10〜60 分で設定可能
- [ ] 機能2 — **20-20-20 目のケアリマインダー**: 20 分ごとに目の休憩を促すポップアップ（20 秒間の焦点移動ガイド付き）
- [ ] 機能3 — **ストレッチガイド**: ブレーク時に首・肩・手首のストレッチをアニメーション付きで 3〜5 種類提示
- [ ] 機能4 — **作業統計ダッシュボード**: 今日の休憩回数・作業時間・スキップ率を新タブページで可視化
- [ ] 機能5 — **vision-focus 連携**: vision-focus がインストール済みの場合、集中セッション終了を検知して自動的にブレーク提案

### Phase 2 以降

- [ ] ウェブカム姿勢検出（TensorFlow.js によるオンデバイス AI）
- [ ] チーム機能: Slack 連携でチームの休憩状況を共有
- [ ] カスタムストレッチルーティン作成
- [ ] ウェアラブル連携（Apple Watch / Garmin）

## ビジネスモデル

| プラン | 価格 | 機能 |
|--------|------|------|
| Free | 無料 | エルゴノミクスタイマー・20-20-20 リマインダー（固定間隔） |
| Pro | $3.99/月 または $29.99/年 | カスタム間隔・ストレッチガイド・ダッシュボード・vision-focus 連携 |
| Team | $2.99/月/人（5人〜） | Pro 全機能 + チーム管理パネル（Phase 2） |

**収益予測（12 ヶ月）**:

- MAU 10,000 人 @ 3% 転換率 = 300 Pro ユーザー
- 月次収益: 300 × $3.99 = **$1,197/月**
- 年間収益: 約 **$14,000**（安定成長後）

参考: 10,000 ユーザー規模の拡張機能は $1,000〜$10,000/月 の収益が一般的（[ExtensionRadar](https://www.extensionradar.com/blog/how-to-monetize-chrome-extension)、2026-03-15 取得）

## 市場規模

| 指標 | 値 | ソース | 取得日 |
|------|-----|--------|--------|
| TAM（B2C ウェルネスアプリ市場） | $12.87B（2025年） → $45.65B（2034年） | [Precedence Research — Wellness Apps Market](https://www.precedenceresearch.com/wellness-apps-market) | 2026-03-15 |
| SAM（Chrome ユーザー × リモートワーカー比率） | 約 8.7 億人（3.83B × 22.8%） | [Backlinko](https://backlinko.com/chrome-users) + [USA Staffing Services](https://www.usastaffingservices.com/does-remote-work-ergonomics-really-matter-for-workers-comp-in-2026/) | 2026-03-15 |
| SOM（1年目目標 MAU） | 50,000 ユーザー | 推定（競合比較・口コミ想定） | 2026-03-15 |
| B2C ウェルネスアプリ CAGR | 15.11%（2025〜2034） | [Precedence Research — Wellness Apps Market](https://www.precedenceresearch.com/wellness-apps-market) | 2026-03-15 |
| AI Chrome 拡張市場 CAGR | 22%（2026〜2033） | [Verified Market Reports](https://www.verifiedmarketreports.com/product/ai-chrome-extension-market/) | 2026-03-15 |

## 技術スタック（提案）

| 領域 | 技術 |
|------|------|
| フロントエンド | TypeScript (strict) / React 18 / Tailwind CSS |
| ビルドツール | Vite + CRXJS（Chrome Extension ビルダー） |
| ストレッチアニメーション | Lottie（軽量アニメーション） |
| ローカルストレージ | Chrome Storage API（クラウド不使用） |
| Phase 2 姿勢検出 | TensorFlow.js（オンデバイス推論） |
| テスト | Vitest / Playwright |
| CI/CD | GitHub Actions |

**月額コスト見積もり**: $0〜$10（GitHub Actions 無料枠 + Netlify Free Tier）

月額 $250 制約に対して余裕あり。Phase 2 の AI 機能追加時も Vercel Pro（$20/月）程度で収まる見込み。

## リスクと対策

| リスク | 影響度 | 対策 |
|--------|--------|------|
| Chrome Manifest V3 対応コスト | 中 | 初期から MV3 前提で設計。Service Worker ベースで実装 |
| 類似ツールとの差別化不足 | 高 | Vision シリーズ連携・ビジュアルガイドの質で差別化。PostureMinder の「通知ズレ」問題を確実に修正 |
| ユーザーが通知を無視する | 中 | フルスクリーンブレーク（PomodoQ 方式）オプションと streak 機能でエンゲージメントを維持 |
| ウェブカム機能のプライバシー懸念（Phase 2） | 高 | Phase 2 はオプトイン + オンデバイス処理のみ。外部送信なし |
| 競合（RiseLoop 等）の機能追加 | 低 | Vision シリーズエコシステムの連携強化で囲い込み |

## データソース・調査方法

### 市場データ

- [Precedence Research — Wellness Apps Market](https://www.precedenceresearch.com/wellness-apps-market) — 信頼度: ★★★ — 取得日: 2026-03-15
- [Verified Market Reports — AI Chrome Extension Market](https://www.verifiedmarketreports.com/product/ai-chrome-extension-market/) — 信頼度: ★★★ — 取得日: 2026-03-15
- [Backlinko — Chrome Users Statistics 2026](https://backlinko.com/chrome-users) — 信頼度: ★★★ — 取得日: 2026-03-15

### 競合分析

- [PostureMinder — Chrome Web Store](https://chromewebstore.google.com/detail/postureminder/dkmkfopiihabelocpelofchappjjnpkm) — 信頼度: ★★★ — 取得日: 2026-03-15
- [PostureMinder — FAQ（通知ズレ問題の公式説明）](https://postureminder.app/faq?c=1) — 信頼度: ★★★ — 取得日: 2026-03-15
- [PostureMinder — Chrome Web Store サポートページ（ユーザーレビュー）](https://chromewebstore.google.com/detail/postureminder/dkmkfopiihabelocpelofchappjjnpkm/support) — 信頼度: ★★★ — 取得日: 2026-03-15
- [RiseLoop — Chrome Web Store](https://chromewebstore.google.com/detail/riseloop-stand-up-timer-b/hhobmbfggpimmmbkgjobngkombglobkm) — 信頼度: ★★★ — 取得日: 2026-03-15
- [eyeCare — Vision & Back Protection (chrome-stats.com)](https://chrome-stats.com/d/pgmnenagoehciiknchfbobbcjdmnmhab) — 信頼度: ★★★ — 取得日: 2026-03-15
- [eyeCare — Chrome Web Store](https://chromewebstore.google.com/detail/eyecare-protect-your-visi/eeeningnfkaonkonalpcicgemnnijjhn) — 信頼度: ★★★ — 取得日: 2026-03-15
- [ExtensionFast — Chrome Extension Trends 2025](https://www.extensionfast.com/blog/the-future-of-chrome-extensions-trends-to-watch-in-2025-and-beyond) — 信頼度: ★★ — 取得日: 2026-03-15

### トレンド情報

- [PMC — Musculoskeletal Pain Among Remote Workers](https://pmc.ncbi.nlm.nih.gov/articles/PMC9800234/) — 信頼度: ★★★ — 取得日: 2026-03-15
- [USA Staffing Services — Remote Work Ergonomics 2026](https://www.usastaffingservices.com/does-remote-work-ergonomics-really-matter-for-workers-comp-in-2026/) — 信頼度: ★★ — 取得日: 2026-03-15
- [ExtensionRadar — Chrome Extension Monetization](https://www.extensionradar.com/blog/how-to-monetize-chrome-extension) — 信頼度: ★★ — 取得日: 2026-03-15

### 調査方法

- WebSearch クエリ: "Chrome extension market size 2025 2026 TAM growth statistics"
- WebSearch クエリ: "Chrome extension trends 2025 most popular categories blue ocean opportunity"
- WebSearch クエリ: "browser posture ergonomics reminder chrome extension 2025 users market gap"
- WebSearch クエリ: "remote work 2025 back pain neck pain computer users statistics percentage"
- WebSearch クエリ: "workplace wellness digital health market size 2025 employee wellbeing software TAM"
- WebFetch: [ExtensionFast](https://www.extensionfast.com/blog/the-future-of-chrome-extensions-trends-to-watch-in-2025-and-beyond) — ブルーオーシャン機会の詳細
- WebFetch: [5ly.co Chrome Extension Ideas 2026](https://5ly.co/blog/chrome-extension-ideas/) — アイデア候補の検証
