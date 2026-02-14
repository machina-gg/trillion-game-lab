---
name: sort-proposals
description: ダッシュボードのチェックボックスを読み取り、提案をディレクトリに振り分けるスキル。
---

# 提案振り分け

## 概要

reports/proposal-dashboard.md のチェックボックス判定を読み取り、提案を適切なディレクトリに移動する。

## 手順

### Step 1: ダッシュボード読み込み

```
Read: reports/proposal-dashboard.md
```

各提案セクションのチェックボックス状態を解析する:

- `[x] adopted` → 採用
- `[x] rejected` → 不採用
- `[x] on-hold` → 保留
- チェックなし → 未確認（処理しない）

### Step 2: バリデーション

各提案について:

- 複数チェックがある場合 → **エラー報告**して処理を中断
  - 「{slug}: 複数のチェックボックスが選択されています。1つだけにしてください。」
- チェックなしの場合 → スキップ（未確認扱い）

### Step 3: ディレクトリ移動

判定された提案を移動する:

```bash
# adopted の場合
mv proposals/inbox/{slug}/ proposals/adopted/{slug}/

# rejected の場合
mv proposals/inbox/{slug}/ proposals/rejected/{slug}/

# on-hold の場合
mv proposals/inbox/{slug}/ proposals/on-hold/{slug}/
```

### Step 4: ダッシュボード更新

移動した提案をダッシュボードから削除する:

- 該当セクション（`## {slug}` から次の `---` まで）を削除
- 未確認の提案はそのまま残す

### Step 5: コミット + PR 作成

```bash
git add proposals/ reports/proposal-dashboard.md
git commit -m "feat: 提案の振り分け（{adopted数}件採用, {rejected数}件不採用, {on-hold数}件保留）"
```

PR を作成する:

```bash
gh pr create --repo machina-gg/trillion-game-lab \
  --title "feat: 提案の振り分け" \
  --body "## Summary
- adopted: {リスト}
- rejected: {リスト}
- on-hold: {リスト}

## 移動内容
{各提案の移動先を記載}"
```

### Step 6: 完了報告

振り分け結果を報告する:

- 採用: {N} 件（{slug リスト}）
- 不採用: {N} 件（{slug リスト}）
- 保留: {N} 件（{slug リスト}）
- 未確認（スキップ）: {N} 件
