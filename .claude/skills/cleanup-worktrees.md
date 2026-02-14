---
name: cleanup-worktrees
description: マージ済みブランチに対応する worktree を一括検出・削除するスキル。マージ後のクリーンアップに使用する。
---

# Worktree クリーンアップ

## 前提

- trillion-game-lab リポジトリで Git Worktree を使った並行開発を行った後に使用する
- マージ済みのブランチに対応する worktree を安全に削除する

## 手順

### 1. マージ済みブランチの検出

```bash
REPO_DIR="/Users/akihiroito/personalwork/git/trillion-game-lab"

# リモートの最新を取得（削除済みブランチも反映）
git -C "$REPO_DIR" fetch origin --prune

# develop にマージ済みの feature ブランチを一覧
git -C "$REPO_DIR" branch --merged origin/develop --list 'feature/*'
```

### 2. 対応する Worktree の特定

```bash
# 現在の worktree 一覧
git -C "$REPO_DIR" worktree list

# マージ済みブランチに対応する worktree をフィルタ
```

### 3. ユーザー確認

**削除前に必ず確認を取る。** 削除対象の一覧を表示し、AskUserQuestion で承認を得る。

表示内容:
- Worktree パス
- 対応するブランチ名
- マージ済みかどうか

### 4. 削除実行

```bash
# worktree を削除
git -C "$REPO_DIR" worktree remove /Users/akihiroito/personalwork/git/trillion-game-lab-{issue-number}

# ブランチを削除
git -C "$REPO_DIR" branch -d "feature/{issue-number}-{description}"
```

### 5. 結果報告

削除した worktree とブランチの一覧を報告する。

## 注意事項

- **未マージの worktree は削除しない**: `--merged` でフィルタしているため、作業中のブランチは対象外
- **`git worktree remove --force` は使わない**: 変更が残っている場合はエラーにして安全を優先する
- **メインリポの worktree は削除しない**: `git worktree list` の最初のエントリ（bare/main）は対象外
