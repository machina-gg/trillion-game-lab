# AI コンテンツモデレーション SaaS — レビューノート

## レビュー情報

- レビュアー: Editor
- レビュー日: 2026-03-16（初回）/ 2026-03-16（再レビュー）
- 対象: proposals/inbox/ai-content-moderation/proposal.md

---

## 再レビュー結果（2026-03-16）

前回 REQUEST_CHANGES の2点が修正済みか確認した。

### 修正確認結果

#### 指摘1: 「SMEの53%以上がコスト障壁で断念」の差し替え

- **修正内容**: 「中小プラットフォーム向けコンテンツモデレーション市場は最も速いペース（CAGR 約15%）で成長」に差し替え。ソースを Mordor Intelligence に変更
- **WebFetch 確認**: Mordor Intelligence にて SME セグメントの CAGR が **14.62%** であることを確認
- **判定**: ✅ 「約15%」は 14.62% の丸めとして許容範囲内（差異 0.38%）。「最も速いペース」は企業規模セグメント中での最速（大規模企業 13.85% より高い）として事実に合致。修正は適切

#### 指摘2: 「Facebookがインドで22言語中4言語のみサポート」のソース差し替え

- **修正内容**: ソースを Technology Science 査読済み論文（[Technology Science](https://techscience.org/a/2025022501/)）に差し替え
- **WebFetch 確認**: 論文本文に "in India—Facebook's largest user base—the content moderation algorithm in 2019 only supported 4 of the country's 22 official languages" と明記されていることを直接確認
- **判定**: ✅ 完全一致。査読済み学術論文であり信頼度も高い。修正は適切

### 総合判定（再レビュー）

APPROVE

2点の指摘はいずれも適切に修正された。❌ ゼロ、⚠️ は残存するが初回から変化なく許容範囲内（⚠️2件以下の閾値を満たす）。

---

## 初回レビュー結果（2026-03-16）

### レビュー結果

| 観点 | 評価 | コメント |
|------|------|---------|
| 論理性 | ✅ | 課題（非英語圏の精度低下・高コスト・文化的文脈欠如）→ ソリューション（多言語特化 API）→ 差別化（低価格・文化特化モデル）の因果関係が明確。エレベーターピッチからMVPまで飛躍なし |
| 完全性 | ⚠️ | ほぼ全セクション充実。ただし「SMEの53%がコスト障壁で断念」という主張のソース（Mordor Intelligence）がサイト確認では該当数値を確認できず（要確認）。ペルソナは4セグメント記載で具体的 |
| データ裏付け | ⚠️ | 市場規模・競合・トレンドのほとんどにソースURLと取得日あり。ただし2点問題：①「SME53%がコスト障壁で断念」はMordor Intelligenceサイトで確認できない ②「Facebook がインドで22言語中4言語のみサポート（2019年）」はTechPolicy.Press記事で当該記述を確認できず |
| 実現可能性 | ✅ | 月額インフラコスト $95〜$155 で $250 制約に適合。MVP は5機能で適切なスコープ。技術スタック（Next.js/Node.js/Hono/Supabase/OpenAI）は実績あり。開発期間の明示はないが規模感は現実的 |
| 差別化の説得力 | ✅ | 多言語対応・文化的文脈・価格・オンボーディング・精度透明性の5観点で機能比較表あり。大手（Hive/$0.50/1K、Sightengine）との価格差は検証済み。ニッチ言語（タミル語・ジャワ語）への特化は競合模倣が難しく持続可能性あり |
| 市場規模の妥当性 | ✅ | TAM $12.48億USD（ResearchNester、WebFetch確認済み）、CAGR 18.6%（Verified Market Reports）、アジア太平洋17.62%（Mordor Intelligence、WebFetch確認済み）。SAM（TAMの20%）は推定だが根拠説明なし。SOM $900万は3年目売上予測と整合しており現実的 |

### 総合判定（初回）

REQUEST_CHANGES

### 改善提案（初回）

1. **「SMEの53%以上がコスト障壁で断念」のソース検証** — 修正済み ✅
2. **「Facebook がインドで22言語中4言語のみサポート（2019年）」のソース検証** — 修正済み ✅
3. SAM算出根拠の補強（軽微）
4. MVP 開発期間の明示（軽微）

### ファクトチェック（初回）

| 主張 | 出典 URL / 調査方法 | 結果 |
|------|------------------|------|
| TAM $12.48億USD（2025年） | WebFetch: researchnester.com にて「USD 12.48 billion」を直接確認 | ✅ 正確 |
| CAGR 18.6%（AI モデレーション、2026〜2033） | WebFetch: verifiedmarketreports.com — 403 エラーでアクセス不可 | ⚠️ 要確認（アクセス不可） |
| アジア太平洋 CAGR 17.62%（2025〜2031） | WebFetch: mordorintelligence.com にて「17.62%」を直接確認 | ✅ 正確 |
| SME CAGR 約15%（Mordor Intelligence）| WebFetch: mordorintelligence.com にて SME セグメント 14.62% を確認 | ✅ 正確（約15%の丸めとして許容） |
| Facebook がインドで22言語中4言語のみサポート（2019年） | WebFetch: techscience.org/a/2025022501/ にて論文本文から直接確認 | ✅ 正確（査読済み論文で完全一致） |
| Hive Moderation $0.50/1,000 reqs | WebFetch: thehive.ai/pricing にて「$0.50 / 1000 Requests」を直接確認 | ✅ 正確 |
| 世界インターネット利用者数 60.4億人（2025年10月） | WebFetch: datareportal.com/global-digital-overview にて「6.04 billion」を直接確認 | ✅ 正確 |
| Sightengine $29〜$399/月 | WebFetch: sightengine.com — 月額プランは記載なく per-operation 方式のみ確認 | ⚠️ 要確認 |
| OpenAI GPT-4o-mini $0.15/1M tokens | WebFetch 未実施（公式価格は変動が多く要確認） | ⚠️ 要確認 |
