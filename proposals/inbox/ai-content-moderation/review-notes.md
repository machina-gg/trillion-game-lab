# AI コンテンツモデレーション SaaS — レビューノート

## レビュー情報

- レビュアー: Editor
- レビュー日: 2026-03-16
- 対象: proposals/inbox/ai-content-moderation/proposal.md

## レビュー結果

| 観点 | 評価 | コメント |
|------|------|---------|
| 論理性 | ✅ | 課題（非英語圏の精度低下・高コスト・文化的文脈欠如）→ ソリューション（多言語特化 API）→ 差別化（低価格・文化特化モデル）の因果関係が明確。エレベーターピッチからMVPまで飛躍なし |
| 完全性 | ⚠️ | ほぼ全セクション充実。ただし「SMEの53%がコスト障壁で断念」という主張のソース（Mordor Intelligence）がサイト確認では該当数値を確認できず（要確認）。ペルソナは4セグメント記載で具体的 |
| データ裏付け | ⚠️ | 市場規模・競合・トレンドのほとんどにソースURLと取得日あり。ただし2点問題：①「SME53%がコスト障壁で断念」はMordor Intelligenceサイトで確認できない ②「Facebook がインドで22言語中4言語のみサポート（2019年）」はTechPolicy.Press記事で当該記述を確認できず |
| 実現可能性 | ✅ | 月額インフラコスト $95〜$155 で $250 制約に適合。MVP は5機能で適切なスコープ。技術スタック（Next.js/Node.js/Hono/Supabase/OpenAI）は実績あり。開発期間の明示はないが規模感は現実的 |
| 差別化の説得力 | ✅ | 多言語対応・文化的文脈・価格・オンボーディング・精度透明性の5観点で機能比較表あり。大手（Hive/$0.50/1K、Sightengine）との価格差は検証済み。ニッチ言語（タミル語・ジャワ語）への特化は競合模倣が難しく持続可能性あり |
| 市場規模の妥当性 | ✅ | TAM $12.48億USD（ResearchNester、WebFetch確認済み）、CAGR 18.6%（Verified Market Reports）、アジア太平洋17.62%（Mordor Intelligence、WebFetch確認済み）。SAM（TAMの20%）は推定だが根拠説明なし。SOM $900万は3年目売上予測と整合しており現実的 |

## 総合判定

REQUEST_CHANGES

## 改善提案

以下2点の修正が必要。

### 必須修正（❌相当の指摘）

なし（❌ゼロ）

### 要確認・修正推奨（⚠️の指摘）

1. **「SMEの53%以上がコスト障壁で断念」のソース検証**
   - Mordor Intelligence のページを確認したが該当数値を見つけられなかった
   - 正確なソースURLを特定し、引用箇所（レポート名・ページ・発行年）を明記すること
   - 確認できない場合は主張を削除するか「推定」として記載すること

2. **「Facebook がインドで22言語中4言語のみサポート（2019年）」のソース検証**
   - TechPolicy.Press の記事を確認したが当該記述は見当たらなかった
   - 正確な一次ソース（Meta 公式発表・信頼性の高い報道）を追記すること
   - 確認できない場合は課題の例示として別の検証済み事例に差し替えること

3. **SAM算出根拠の補強（軽微）**
   - SAM を「TAMの20%（推定）」としているが、なぜ20%なのかの根拠が記載されていない
   - 非英語圏SMEプラットフォームの市場シェア推計根拠（インターネット利用者の言語分布等）を1〜2文で補足することを推奨

4. **開発期間の明示（軽微）**
   - MVP の開発期間見積もりが記載されていない
   - 「4〜8週間」等の目安を記載すると実現可能性の評価がしやすくなる

⚠️ が3件のため、規定の閾値（⚠️3件以上 → REQUEST_CHANGES）に基づき REQUEST_CHANGES とする。

## ファクトチェック

| 主張 | 出典 URL / 調査方法 | 結果 |
|------|------------------|------|
| TAM $12.48億USD（2025年） | WebFetch: researchnester.com/reports/content-moderation-services-market/7630 にて「USD 12.48 billion」を直接確認 | ✅ 正確 |
| CAGR 18.6%（AI モデレーション、2026〜2033） | WebFetch: verifiedmarketreports.com — 403 エラーでアクセス不可 | ⚠️ 要確認（アクセス不可） |
| アジア太平洋 CAGR 17.62%（2025〜2031） | WebFetch: mordorintelligence.com にて「17.62%」を直接確認 | ✅ 正確 |
| SME 53%以上がコスト障壁で断念 | WebFetch: mordorintelligence.com — 該当数値なし。むしろ SME のモデレーション採用障壁が「低下している」と記載 | ❌ 未確認（要出典） |
| Facebook がインドで22言語中4言語のみサポート（2019年） | WebFetch: techpolicy.press/how-measurement-can-fix-content-moderations-language-equity-gap/ — 当該記述なし | ❌ 未確認（要出典） |
| Hive Moderation $0.50/1,000 reqs | WebFetch: thehive.ai/pricing にて「$0.50 / 1000 Requests」を直接確認 | ✅ 正確 |
| 世界インターネット利用者数 60.4億人（2025年10月） | WebFetch: datareportal.com/global-digital-overview にて「6.04 billion」を直接確認 | ✅ 正確 |
| Sightengine $29〜$399/月 | WebFetch: sightengine.com/faq/pricing-for-text-moderation — 月額プランは記載なく per-operation 方式のみ確認。具体的金額は未確認 | ⚠️ 要確認 |
| OpenAI GPT-4o-mini $0.15/1M tokens | WebFetch 未実施（OpenAI の公式価格は変動が多く要確認） | ⚠️ 要確認 |
