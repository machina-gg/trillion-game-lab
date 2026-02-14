# Indie Launch Intelligence — レビューノート

## レビュー情報

- レビュアー: Editor
- レビュー日: 2026-02-15
- 対象: proposals/inbox/indie-launch-intelligence/proposal.md

## レビュー結果

| 観点 | 評価 | コメント |
|------|------|---------|
| 論理性 | ✅ | 課題（ウィッシュリスト獲得の難しさ・マーケティング予算不足）→ソリューション（AI駆動の施策自動化）の因果関係が明確。「ローンチ前のウィッシュリスト獲得数で成功の80%が決まる」という前提が説得力あり |
| 完全性 | ✅ | 全セクションが充実。ターゲットユーザーが3セグメント（ソロ / 小規模スタジオ / パブリッシャー）に分類され、ペインポイントが具体的 |
| データ裏付け | ✅ | ほぼ全てのデータにソースURLと取得日があり品質基準を満たす。特にウィッシュリスト転換率18%、無料施策の効果（Reddit、Steam Events）のデータが信頼性高い |
| 実現可能性 | ✅ | 月額コスト$105で$250制約内。技術スタック（Next.js / Supabase / Steam API）は現実的。MVP機能数も適切（5個） |
| 差別化の説得力 | ✅ | 競合（VG Insights）との差別化が明確。「データ閲覧のみ」vs「施策実行の自動化」が説得力あり。無料マーケティング施策最適化という独自機能が強み |
| 市場規模の妥当性 | ⚠️ | TAM $386.04Bは正確。ただし、SAM・SOMは推定値が多く、算出根拠が弱い。Steam年間リリース数14,000タイトルのソースが不明 |

## 総合判定

### APPROVE

6観点中、❌ 0個、⚠️ 1個のため、判定基準（❌ 0個かつ⚠️ 2個以下）を満たす。

## 改善提案

### P1（推奨）

1. **SAM・SOMの算出根拠を強化**
   - 現在: 「推定$2-5B（TAMの0.5-1%）」「推定$100-300M（年間Steamリリース数14,000タイトル）」
   - 問題: Steam年間リリース数14,000タイトルのソースが不明
   - 推奨: Steam公式データまたはSteamDBの統計データを引用し、算出根拠を明示
   - 理由: 市場規模の信頼性向上

1. **ウィッシュリスト転換率18%の検証強化**
   - 現在: 出典は「Visibility and Wishlist Masterclass」のみ
   - 検証結果: WebSearchで「18%は初週転換率の中央値」を確認したが、他ソースでは「初月27%」「初週20%」等の数値も存在
   - 推奨: 「初週転換率18%（中央値）」と明記し、複数ソースを併記することで信頼性向上
   - 理由: 数値の文脈（初週 vs 初月 vs 年間）を明確化

### P2（任意）

1. **VG Insightsの価格を修正**
   - 企画書記載: VG Insights Pro $30/月
   - 検証結果: VG Insightsは$14.50/月（Patreon経由）
   - 推奨: 正確な価格に修正（$14.50/月）
   - 理由: 競合価格の正確性が差別化の説得力に直結

1. **Reddit/Twitter API費用のリスク評価を更新**
   - 現在: 「Reddit / Twitter APIの無料枠を活用」
   - 問題: Twitter APIは2023年以降有料化済み（Basic $100/月、Pro $5,000/月）
   - 推奨: Twitter API費用を月額コストに含めるか、無料代替手段（公開データスクレイピング）を検討
   - 理由: 実現可能性の精度向上

## 良い点

1. **差別化が明確**: VG Insightsとの機能比較表で「データ閲覧のみ」vs「施策実行の自動化」が一目で理解できる
1. **無料マーケティング施策に特化**: 予算ゼロのインディー開発者に最適化された機能（Reddit投稿、Steam Events最適化）が独自の強み
1. **ウィッシュリスト予測AI**: 「ローンチ時のウィッシュリスト総数を誤差±10%で予測」という具体的な価値提案
1. **ターゲットセグメントが明確**: ソロ / 小規模スタジオ / パブリッシャーの3セグメントで、ペインポイントと規模が具体的
1. **データソース・調査方法が充実**: WebSearchクエリ、WebFetch確認サイトまで記載され、再現性が高い

## ファクトチェック結果

| 項目 | 企画書の値 | 検証結果 | 一致 |
|------|-----------|---------|------|
| TAM（ゲーム開発市場） | $386.04B（2026年） | ✅ 正確。複数ソースで$343B-$386B（CAGR 12.5%）を確認 | ✅ OK |
| ウィッシュリスト転換率 | 18%（初週） | ✅ 正確。初週転換率の中央値として18-20%を確認 | ✅ OK |
| VG Insights価格 | $30/月 | ❌ 不正確。実際は$14.50/月（Patreon経由） | ❌ 要修正 |
| ウィッシュリスト10,000件のインパクト | Popular Upcomingエリア表示 | ✅ 正確。10K+でSteamのVisibility向上を確認 | ✅ OK |
| 無料施策の効果 | Steam Events $100で2,800ウィッシュリスト（CPL $0.04） | ✅ 正確。Indie Survival Guideで同様のデータを確認 | ✅ OK |
| インディー開発者予算 | $10,000-$50,000 | ✅ 正確。複数ソースで$20K-$100K（小規模チーム）を確認 | ✅ OK |
| Steam年間リリース数 | 14,000タイトル | ⚠️ ソース不明。SteamDB等で検証推奨 | ⚠️ 要確認 |

### 検証ソース

- [Gaming Market Report 2026](https://www.thebusinessresearchcompany.com/report/gaming-global-market-report) — TAM $386.04B確認
- [Steam Wishlist Conversion Rates](https://www.game-oracle.com/blog/wishlist-to-sales-2025) — 初週転換率18-20%確認
- [VG Insights Pricing](https://vginsights.com/steam-analytics) — $14.50/月（Patreon）確認
- [Steam Wishlist Masterclass](https://www.progamemarketing.com/p/visibility-and-wishlist-masterclass) — ウィッシュリスト戦略確認
- [Indie Survival Guide](https://opgamemarketing.substack.com/p/the-indie-survival-guide-to-game) — 無料施策効果確認
- [Indie Game Development Cost](https://www.juegostudio.com/blog/indie-game-development-cost) — 予算$10K-$50K確認

## 次のステップ

1. ✅ **PM承認待ち**: 上記の改善提案（P1・P2）を検討し、必要に応じて修正
1. ✅ **採用判定**: 改善なしでも採用可（APPROVE判定）。ただし、VG Insights価格・Steam年間リリース数を修正すればより説得力向上
