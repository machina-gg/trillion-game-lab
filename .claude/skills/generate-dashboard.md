---
name: generate-dashboard
description: proposals/inbox/ を走査し、提案ダッシュボード（reports/proposal-dashboard.md）を生成・更新するスキル。
---

# 提案ダッシュボード生成

## 概要

proposals/inbox/ 内の各提案から概要を抽出し、reports/proposal-dashboard.md にダッシュボードを生成する。
既存のチェックボックス判定は保持される。

## 手順

### Step 1: 既存ダッシュボードの読み込み

```
Read: reports/proposal-dashboard.md
```

ファイルが存在する場合、各提案のチェック状態を記録しておく:

- `[x] adopted` / `[x] rejected` / `[x] on-hold` の状態を slug ごとに保存

### Step 2: proposals/inbox/ の走査

```bash
ls proposals/inbox/
```

各 `proposals/inbox/{slug}/proposal.md` を読み込み、以下を抽出する:

- **概要**: エレベーターピッチ（1-2行）
- **市場規模**: TAM の値
- **ステータス**: proposal.md 内の Status フィールド

### Step 3: ダッシュボード生成

`reports/proposal-dashboard.md` を以下のフォーマットで生成する:

```markdown
# 提案ダッシュボード

> 判定: 1つだけチェックしてください。チェックなし = 未確認

---

## {slug}

- **概要**: {エレベーターピッチ}
- **市場規模**: TAM {値}
- **詳細**: [企画書](../proposals/inbox/{slug}/proposal.md)

判定:
- [ ] adopted
- [ ] rejected
- [ ] on-hold

---
```

### Step 4: 既存チェック状態の復元

Step 1 で保存したチェック状態を復元する。
slug が一致する提案は、以前のチェック状態を維持する。

### Step 5: 完了報告

ダッシュボードに含まれる提案数を報告する:

- 新規追加: {N} 件
- 既存維持: {N} 件
- inbox から削除済み（ダッシュボードから除外）: {N} 件
