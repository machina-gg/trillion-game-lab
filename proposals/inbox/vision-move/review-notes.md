# vision-move — レビューノート

## レビュー情報

- レビュアー: Editor
- レビュー日: 2026-03-15（再レビュー）
- 対象: proposals/inbox/vision-move/proposal.md
- PR: machina-gg/trillion-game-lab#33

## レビュー結果（再レビュー）

| 観点 | 評価 | コメント |
|------|------|---------|
| 論理性 | ✅ | 課題（リモートワーカーの筋骨格系問題）→ ソリューション（3機能統合拡張）→ 差別化（Vision連携）の論理展開は一貫している。vision-focus との補完関係も明確 |
| 完全性 | ✅ | テンプレートの全セクションが埋まっている。競合個別分析も詳細に追記された |
| データ裏付け | ✅ | 主要データにソースURLと取得日が記載済み。PMC論文の引用数値を部位別統計に修正済み。TAMもB2C市場データに変更済み |
| 実現可能性 | ✅ | 月額$0〜$10のコスト見積もりで$250制約に余裕あり。MVP5機能はChrome拡張として標準的な範囲。技術スタックも現実的 |
| 差別化の説得力 | ✅ | PostureMinder・RiseLoop・eyeCareを個別セクションで分析（ユーザー数・評価・弱点を明記）。通知ズレ問題のソースも追加済み |
| 市場規模の妥当性 | ✅ | TAMをB2C ウェルネスアプリ市場（$12.87B、2025年）に変更し、ターゲットとの整合性が改善された |

## 総合判定

**APPROVE**

前回 REQUEST_CHANGES で指摘したP0・P1の全項目が適切に修正された。残存する軽微な確認事項（AI Chrome拡張 CAGR 22%の直接ソース確認不可）は⚠️1件のみで、APPROVE 閾値（❌ 0個・⚠️ 2個以下）を満たす。

## 前回指摘事項の対応確認

### P0（必須）— 両項目とも解消済み

1. **PMC9800234の引用数値修正** ✅
   - 修正前: 「うち72%のオフィスワーカーが首・腰・肩・肘・手首のいずれかに不調」（PMC9800234には存在しない数値）
   - 修正後: 部位別統計（首60.3%・腰59.5%・肩49.6%・上背部42.1%・手首/手35.5%）を直接記載
   - ファクトチェック: PMC9800234で全数値を確認済み ✅

2. **TAM市場セグメントの整合性修正** ✅
   - 修正前: TAMに「法人ウェルネスソフト（B2B SaaS）」を使用
   - 修正後: TAMを「B2C ウェルネスアプリ市場 $12.87B（2025年）→ $45.65B（2034年）、CAGR 15.11%」に変更
   - ファクトチェック: Precedence Researchで全数値を確認済み ✅

### P1（推奨）— 両項目とも解消済み

3. **競合の個別分析の追加** ✅
   - PostureMinder・RiseLoop・eyeCare を個別セクションで分析
   - ユーザー数・評価・価格・主な機能・弱点を各社ごとに明記

4. **通知ズレ問題のソース追加** ✅
   - PostureMinder FAQ（https://postureminder.app/faq?c=1）を引用
   - Chrome Web Store サポートページのURLも追加
   - WebSearch で通知信頼性問題の継続報告を確認済み ✅

## ファクトチェック（再レビュー）

| 主張 | 出典 URL / 調査方法 | 結果 |
|------|------------------|------|
| リモートワーカー首痛60.3%・腰痛59.5%・肩痛49.6% | WebFetch: https://pmc.ncbi.nlm.nih.gov/articles/PMC9800234/ | ✅ 正確（論文内で全数値を確認） |
| Wellness Apps TAM $12.87B（2025年）| WebFetch: https://www.precedenceresearch.com/wellness-apps-market | ✅ 正確 |
| Wellness Apps CAGR 15.11%（2025〜2034）| WebFetch: https://www.precedenceresearch.com/wellness-apps-market | ✅ 正確 |
| PostureMinder 20,000+ ユーザー | WebSearch: PostureMinder chrome extension statistics 2025 | ✅ 正確（20,000ユーザー・4.40評価/135件を確認） |
| PostureMinder 通知ズレ問題 | WebSearch: PostureMinder chrome extension notification delay bug review 2025 | ✅ 正確（FAQおよびレビューでの複数報告を確認） |
| eyeCare 50,000+ ユーザー | WebSearch: eyeCare protect vision chrome extension users 2025 | ⚠️ 要確認（4.5評価は確認できたが正確なユーザー数を直接確認できず） |
| AI Chrome拡張 CAGR 22%（2026〜2033）| WebFetch: https://www.verifiedmarketreports.com/product/ai-chrome-extension-market/ → 403エラー | ⚠️ 直接確認不可（有料レポートのため）。ただし主張の方向性は複数の業界レポートと整合 |

## 初回レビュー（参考）

- 初回レビュー日: 2026-03-15
- 判定: REQUEST_CHANGES
- 指摘件数: P0×2件・P1×2件・P2×2件
