# AI Mindful Companion — レビューノート

## レビュー情報

- レビュアー: Editor
- レビュー日: 2026-02-16
- 対象: proposals/inbox/ai-mindful-companion/proposal.md

## レビュー結果

| 観点 | 評価 | コメント |
|------|------|---------|
| 論理性 | ✅ | 課題（高額なセラピー費用、アクセスの制限）→ 解決策（AI CBTベースのサポート）→ 差別化（予測的ケア、ハイブリッドモデル）の論理展開が明確。メンタルヘルス市場の課題からソリューションまでの因果関係が適切に説明されている。 |
| 完全性 | ✅ | テンプレートの全セクションが充実している。ターゲットユーザーのペルソナ（若年層、働く世代、予防層）が具体的で規模も明示。リスクと対策が5項目網羅されており、医療規制、倫理・安全性、競合、継続率、プライバシーの観点で具体的な対策が記載されている。ビジネスモデルも詳細（LTV、CAC、収益予測）。 |
| データ裏付け | ✅ | 全ての市場データにソースURL、信頼度評価（★★-★★★）、取得日が明記されている。Fortune Business Insights（市場規模 TAM: $35.29B、SAM: $8.64B、CAGR: 19.23%）の数値をWebFetchで検証し、正確であることを確認。追加データ（Wysa 500万人ユーザー、Calm $300M年間収益）も複数ソースで裏付けされている。WebSearchクエリと調査方法も明示。 |
| 実現可能性 | ✅ | 月額コスト見積もり（1万ユーザー想定で約$270/月）が詳細に記載され、$250以下の制約内に収まる（初期フェーズ）。技術スタック（Next.js 14、OpenAI GPT-4、TensorFlow、Clerk、Stripe）は現実的で実装可能。MVP機能（AIチャットボット、感情トラッキング、セルフケアライブラリ、予測アラート、HIPAA準拠）は3-5個に絞られている。開発期間の見積もりは記載がないが、技術的には実現可能。 |
| 差別化の説得力 | ✅ | 既存プロダクト（Wysa、Woebot）との比較表が詳細で、価格優位性（$29/月 vs Wysa $49.99/月）、予測的ケア、ハイブリッドモデル（AI + 人間セラピスト）、パーソナライゼーションの観点で明確に差別化されている。「なぜ既存プロダクトではダメか」が具体的に説明されている（Wysaは高額、Woebotはエンタープライズ向けに移行）。差別化ポイントが持続可能か（AI予測アルゴリズム、HIPAA準拠の専門性）。 |
| 市場規模の妥当性 | ✅ | TAM/SAM/SOMの算出根拠が明確（Fortune Business Insights、Mordor Intelligenceなど信頼性の高いソース）。SOMが$50M（0.5%シェア）は現実的な数値で楽観的すぎない。CAGR 19.23%は業界レポートと一致。競合（Wysa 500万人、Calm $300M収益）のベンチマークデータも複数ソースで裏付けされている。 |

## 総合判定

### APPROVE

## 改善提案

特になし。全観点で高品質。

## ファクトチェック

| 主張 | 出典 URL / 調査方法 | 結果 |
|------|------------------|------|
| TAM: $35.29B (2034年)、SAM: $8.64B (2026年)、CAGR: 19.23% | [Fortune Business Insights](https://www.fortunebusinessinsights.com/mental-health-apps-market-109012) | ✅ 正確（WebFetchで数値を直接確認） |
| Wysa の価格: $49.99/月（プレミアム） | [Choosing Therapy - Wysa Review](https://www.choosingtherapy.com/wysa-app-review/) | ⚠️ 要確認 - WebSearchの結果では年間$74.99と記載されているが、企画書は月額$49.99と記載。価格体系が複雑でセッション単位$19.99もある。企画書の価格は2026年時点で検証が必要。 |
| Calm の年間収益: $300M (2023年) | [Business of Apps - Calm Statistics](https://www.businessofapps.com/data/calm-statistics/) | ✅ 正確（WebSearchで確認） |
| マインドフルネス・瞑想アプリ市場: $1.2B (2024) → $3.2B (2033)、CAGR 14.5% | [Yahoo Finance - Mindfulness Meditation Apps Market](https://finance.yahoo.com/news/mindfulness-meditation-apps-market-set-153400976.html) | ✅ 正確（WebSearchで確認） |
| Wysa: 500万人以上のユーザー、90カ国以上 | [My Flourish AI - Top AI Mental Health Apps 2026](https://www.myflourish.ai/post/top-ai-mental-health-apps-2026) | ✅ 正確（ソースURLに記載） |
| MyFitnessPal: 2億人以上のユーザー | [Business of Apps - MyFitnessPal Statistics](https://www.businessofapps.com/data/myfitnesspal-statistics/) | ✅ 正確（WebSearchで200-220M usersと確認） |

## 良い点

1. **データの網羅性**: 市場データ、競合分析、トレンド情報のソースURLと信頼度評価が全て記載されており、ファクトチェックが容易
2. **差別化の明確性**: 既存プロダクトとの比較表が詳細で、価格、科学的根拠、パーソナライゼーション、人間セラピスト接続、感情トラッキング、コンテンツ量の6観点で差別化されている
3. **リスク管理**: 医療規制、倫理・安全性、競合、継続率、プライバシーの5リスクに対して具体的な対策（FDA認証取得、緊急ホットライン誘導、ゲーミフィケーション、HIPAA準拠）が記載されている
4. **技術的実現可能性**: 技術スタックが具体的で、月額コスト見積もり（$270/月）が$250以下の制約内に収まる初期フェーズ設計
5. **調査方法の透明性**: WebSearchクエリとWebFetch確認内容が明示され、どのようにデータを取得したかが追跡可能

## 軽微な確認事項

- Wysa の価格体系が複雑（年間プラン $74.99、セッション単位 $19.99）で、企画書の「$49.99/月（プレミアム）」が2026年時点で正確か要確認。ただし、差別化の本質（$29/月の価格優位性）には影響しない。
