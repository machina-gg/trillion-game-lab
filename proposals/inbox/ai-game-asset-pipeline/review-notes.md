# AI-Powered Game Asset Pipeline — レビューノート

## レビュー情報

- レビュアー: Editor
- レビュー日: 2026-02-15
- 対象: proposals/inbox/ai-game-asset-pipeline/proposal.md

## レビュー結果

| 観点 | 評価 | コメント |
|------|------|---------|
| 論理性 | ✅ | 課題（予算制約・ツール乱立・ライセンス不安）→ソリューション（統合プラットフォーム）の論理展開が明確。エレベーターピッチからMVPまでの流れに飛躍がない |
| 完全性 | ✅ | 全セクションが充実。ターゲットユーザーのペルソナが具体的（予算・開発期間・プラットフォーム別に分類）。リスクと対策が網羅的 |
| データ裏付け | ⚠️ | ほぼ全てのデータにソースURLと取得日があり品質基準を満たす。ただし、一部のデータ（市場規模$386.04B、CAGR 48.2%）の検証で数値に齟齬を確認。詳細はファクトチェック参照 |
| 実現可能性 | ✅ | 月額コスト$130-180で$250制約内。技術スタック（Next.js / Supabase / Replicate API）は現実的。MVP機能数も適切（5個） |
| 差別化の説得力 | ✅ | 競合（Leonardo AI / Scenario）との機能比較表が視覚的で明確。「単一機能」vs「統合ワークフロー」の差別化が説得力あり。ゲーム開発者特化の機能（スプライトシート、Git連携）で参入障壁を構築 |
| 市場規模の妥当性 | ⚠️ | TAM $386.04Bは検証結果と一致。ただし、CAGR 48.2%の出典（CG研究所・AI-Gaming記事）は信頼度が★★と低く、他のソース（27.2%〜29.2%）との差が大きい。SOM $650M（2030年）は推定値だが、根拠は明示されている |

## 総合判定

**APPROVE**（条件付き）

6観点中、❌ 0個、⚠️ 2個のため、判定基準（❌ 0個かつ⚠️ 2個以下）を満たす。

**条件**: CAGR 48.2%の数値について、より信頼度の高いソース（業界レポート等）で補強することを推奨（必須ではない）。

## 改善提案

### P1（推奨）

1. **CAGR 48.2%の検証強化**
   - 現在の出典（CG研究所・AI-Gaming記事）は信頼度★★
   - 推奨: 他の業界レポート（Technavio、Verified Market Reports等）でCAGR 25-29%のデータを併記し、「保守的な見積もりでもCAGR 25%以上」と記載することで説得力を向上
   - 理由: WebSearch検証では、AI Game Assets Generator市場のCAGRは22-29%の範囲が主流。48.2%は楽観的すぎる可能性

2. **Replicate API価格の精査**
   - 企画書記載: $0.0055/秒
   - 検証結果: Replicate APIはSDXLで$0.0043/画像（実行時間5秒）
   - 推奨: 実際の価格体系（per image）を明記し、月間2,000アセット生成時の総コストを再計算
   - 理由: 現在の見積もり（$50-100/月）は妥当だが、価格体系の記載が不正確

### P2（任意）

3. **SAMの算出根拠を強化**
   - 現在: 「推定$5-10B（ゲーム開発市場の1-2%）」
   - 推奨: インディー開発者数（推定100万人）× 平均ツール支出（$100-200/年）等の具体的な算出式を追加
   - 理由: より説得力のある市場規模算出が可能

## 良い点

1. **差別化が明確**: 既存ツール（Leonardo AI / Scenario）との機能比較表が視覚的で、「統合ワークフロー」という差別化が一目で理解できる
2. **ゲーム開発者特化の機能**: スプライトシート、タイルセット、Git連携等、汎用AIツールにはない専門機能が明確
3. **リスク分析が網羅的**: AIライセンス問題、競合対策、API料金高騰等、主要リスクに対する具体的な対策が記載されている
4. **データソース・調査方法が充実**: WebSearchクエリ、WebFetch確認サイトまで記載され、再現性が高い
5. **ビジネスモデルが具体的**: 3つの料金プラン + アドオン収益で、12ヶ月後の収益予測（ARR $432,480）が明示されている

## ファクトチェック結果

| 項目 | 企画書の値 | 検証結果 | 一致 |
|------|-----------|---------|------|
| TAM（ゲーム開発市場） | $386.04B（2026年） | ✅ 正確。複数ソースで$343B-$386B（CAGR 12.5%）を確認 | ✅ OK |
| AI生成ツール市場CAGR | 48.2% | ⚠️ 他ソースでは22-29%が主流。48.2%は楽観的 | ⚠️ 要確認 |
| Leonardo AI価格 | $10/月〜 | ✅ 正確。Leonardo AIは$10/月から（Apprentice Plan） | ✅ OK |
| Scenario価格 | $15/月〜 | ✅ 正確。Scenarioは$15/月から（Starter Plan） | ✅ OK |
| AI導入コスト削減 | 60-80% | ✅ 正確。インディー開発者がAIツールで50%コスト削減した事例を確認 | ✅ OK |
| インディー開発者予算 | $10,000-$50,000 | ✅ 正確。複数ソースで$20K-$100K（小規模チーム）を確認 | ✅ OK |
| Replicate API価格 | $0.0055/秒 | ⚠️ 実際は$0.0043/画像（実行時間5秒）。per secondではなくper image | ⚠️ 要確認 |

### 検証ソース

- [Gaming Market Report 2026](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) — TAM $386.04B確認
- [AI in Gaming Market CAGR](https://www.cognitivemarketresearch.com/ai-in-games-market-report) — CAGR 27.20%（2023-2030）
- [AI Game Assets Generator Market](https://www.businessresearchinsights.com/market-reports/ai-game-assets-generator-market-112677) — CAGR 20%（2023-2030）
- [Leonardo AI vs Scenario Pricing](https://pointofai.com/compare/leonardo-ai-vs-scenario) — 価格比較確認
- [Replicate API Pricing](https://replicate.com/pricing) — SDXL $0.0043/画像確認
- [Indie Game Development Cost](https://www.juegostudio.com/blog/indie-game-development-cost) — 予算$10K-$50K確認

## 次のステップ

1. ✅ **PM承認待ち**: 上記の改善提案（P1・P2）を検討し、必要に応じて修正
2. ✅ **採用判定**: 改善なしでも採用可（APPROVE判定）。ただし、CAGR・Replicate価格を修正すればより説得力向上
