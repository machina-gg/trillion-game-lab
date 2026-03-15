# WCAG Guardian — レビューノート

## レビュー情報

- レビュアー: Editor
- レビュー日: 2026-03-16
- 対象: proposals/inbox/wcag-guardian/proposal.md

## レビュー結果

| 観点 | 評価 | コメント |
|------|------|---------|
| 論理性 | ✅ | 課題（ウィジェットの限界・訴訟急増・高コスト）→ ソリューション（コードレベル修正＋証明書自動生成）→ 差別化の因果関係が明確。エレベーターピッチから MVP まで論理の飛躍なし |
| 完全性 | ✅ | エレベーターピッチ・課題・ターゲット・差別化・MVP・ビジネスモデル・市場規模・技術スタック・リスク対策・データソースが全て記載済み |
| データ裏付け | ⚠️ | 全データにソース URL と取得日あり。ただし自動ツールの検出率「30%」はソースが「30〜40%」と幅を持つ記述で、企画書が下限値のみ引用している点は要確認。SMB 割合「77%」の出典 AudioEye は自社レポートで第三者独立性に留意が必要 |
| 実現可能性 | ✅ | 月額 $105（$250 制約内）。技術スタックは Next.js/Supabase/axe-core/Puppeteer と標準的。MVP 機能は 5 つ（上限内）。axe-core OSS を活用し開発コストを最小化する設計が現実的 |
| 差別化の説得力 | ✅ | 比較表で accessiBe・UserWay との機能差を明確に図示。「ウィジェットが訴訟対策にならない」という判例ベースの主張は強力かつ持続可能な差別化ポイント |
| 市場規模の妥当性 | ⚠️ | TAM/CAGR は Mordor Intelligence の数値と一致し信頼性は高い。ただし SAM 算出（TAM × 北米 39.87% × SMB 17%）の「SMB 17%」の根拠が不明。SOM（SMB 市場の 0.5% = $1.6M ARR）は保守的で現実的だが、SAM の根拠補強が必要 |

## 総合判定

REQUEST_CHANGES

## 改善提案

### P1（推奨）— 改善すると品質が大幅向上する

1. **自動検出率の記述を正確化**（データ裏付け）
   - 現状: 「自動ツールが検出できる WCAG 違反は全体の 30%」
   - 出典（Accessibility.Works）は「30〜40%」と記載
   - 修正案: 「自動ツールが検出できる WCAG 違反は全体の 30〜40% に留まる」に変更、またはより保守的な下限値を使う場合は引用元の幅を注記する

2. **SAM 算出の SMB 17% 根拠を追記**（市場規模の妥当性）
   - TAM × 北米 39.87% は Mordor Intelligence から明確に引用されているが、「SMB 17%」の出典が記載されていない
   - 修正案: 出典 URL と取得日を追記（例: Mordor Intelligence の同レポート内セグメント別データ、または Grand View Research 等）

3. **ウィジェット訴訟件数の数字の一貫性確認**（データ裏付け）
   - 「コンセプト」セクション: 「2024 年に提起された 4,187 件の ADA 訴訟のうち 22.64% はウィジェット導入済みサイト」（= 約 948 件）
   - 「課題 1」セクション: 「2024 年の ADA 訴訟 4,187 件のうち 1,023 件（25%）がウィジェット導入済みサイト」
   - UsableNet レポートは「Over 1,000 businesses, accounting for more than 25%」と記述
   - 修正案: 22.64% と 25% の数値の不一致を統一し、正確な引用に修正する（UsableNet ソースに合わせて「1,000 件超（25% 以上）」と記述）

### P2（任意）— あると品質が向上する

1. **AudioEye レポートの第三者性を補足**（データ裏付け）
   - 「訴訟対象の 77% が SMB」の出典は AudioEye（競合他社の自社レポート）
   - 独立した第三者機関（UsableNet・EcomBack・法律事務所等）による同趣旨のデータを補完ソースとして追記することを推奨

2. **収益予測の CAC 根拠を追記**（完全性）
   - CAC「$80〜120」の算出根拠（コンテンツマーケティング・SEO の想定コスト）が記載されていない
   - 類似 SaaS の実績値や業界平均を参考データとして追記すると説得力が増す

## ファクトチェック結果

| 主張 | 出典 URL / 調査方法 | 結果 |
|------|------------------|------|
| 2024年 ADA 訴訟 4,187 件 | [UsableNet 2024 Report](https://blog.usablenet.com/2024-digital-accessibility-lawsuit-report-relased-insights-for-2025) を WebFetch で確認 | ⚠️ 「Over 4,000」と記述あり。4,187 という具体数は確認できず要確認 |
| ウィジェット導入済みサイトへの訴訟 22.64%（コンセプト欄） | UsableNet 2024 Report を WebFetch で確認 | ❌ ソースは「over 1,000 businesses, over 25%」と記述。22.64% という数値は不一致 |
| ウィジェット導入済みサイトへの訴訟 1,023 件（25%）（課題 1 欄） | UsableNet 2024 Report を WebFetch で確認 | ✅ 「Over 1,000, more than 25%」と概ね一致 |
| 2025 年上半期 ADA 訴訟 2,014 件（前年比 +37%） | [EcomBack 2025 Mid-Year Report](https://www.ecomback.com/ada-website-lawsuits-recap-report/2025-mid-year-ada-website-lawsuit-report) を WebFetch で確認 | ✅ 正確に一致 |
| 自動ツールの WCAG 検出率 30% | [Accessibility.Works](https://www.accessibility.works/blog/saas-platform-ada-wcag-compliance-cost/) を WebFetch で確認 | ⚠️ ソースは「30〜40%」と幅あり。30% のみの引用は要修正 |
| TAM $0.79B（2025）→ $1.15B（2031）、CAGR 6.23% | [Mordor Intelligence](https://www.mordorintelligence.com/industry-reports/digital-accessibility-software-market) を WebFetch で確認 | ✅ 正確に一致 |
| 北米市場シェア 39.87% | Mordor Intelligence を WebFetch で確認 | ✅ 正確に一致 |
| accessiBe 年額 $490〜 | [accessiBe 公式](https://accessibe.com/pricing/accesswidget) を WebFetch で確認 | ✅ Micro プラン $490/年を確認 |
| 訴訟対象の 77% が SMB（売上 $25M 以下） | AudioEye 2025 Report（WebFetch で 429 エラー、直接確認不可） | ⚠️ 要確認（AudioEye は競合他社の自社レポートであり第三者性に留意） |

## 良い点

- 「ウィジェットが訴訟対策にならない」という痛点を判例ベースで示しており、課題提起の説得力が高い
- TAM/CAGR/北米シェアが Mordor Intelligence で正確に裏付けられており、市場データの信頼性が高い
- 月額 $105 という具体的なコスト内訳が明示されており、$250 制約への適合が明確
- 価格比較表・機能比較表により差別化が視覚的に理解しやすい
- リスクと対策が 5 項目にわたって網羅されており、事業の現実認識が適切
- データソース・調査方法セクションが充実しており、信頼度評価まで記載されている
