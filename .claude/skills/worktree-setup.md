---
name: worktree-setup
description: Git Worktree のセルフサービス作成・管理手順。全エージェントが作業開始時に必ず実行する。
---

# Worktree セルフサービス（必須）

## 概要

エージェント（Researcher / Planner / Editor）は作業開始時に必ず Worktree を作成する。
メインリポのワーキングディレクトリは PM 専用。PM の指示は不要（セルフサービス）。

## 作成条件

Issue 番号が紐づいている作業は常に Worktree を作成する。

## 作成手順

```bash
# 1. 最新の develop を取得
git -C /Users/akihiroito/personalwork/git/trillion-game-lab fetch origin

# 2. Worktree を作成（命名: trillion-game-lab-{issue-number}）
git -C /Users/akihiroito/personalwork/git/trillion-game-lab worktree add \
  /Users/akihiroito/personalwork/git/trillion-game-lab-{issue-number} \
  -b "feature/{issue-number}-{description}" origin/develop
```

## 配置場所

メインリポの兄弟ディレクトリに配置する:

```
/Users/akihiroito/personalwork/git/
├── trillion-game-lab/              ← メインリポ（PM 専用。develop ブランチ）
├── trillion-game-lab-10/           ← Issue #10 用 worktree（Researcher）
├── trillion-game-lab-11/           ← Issue #11 用 worktree（Planner）
└── trillion-game-lab-12/           ← Issue #12 用 worktree（Editor）
```

## 作業時の注意

- **ファイル操作**: 絶対パスで worktree 内のファイルを操作する
  ```
  /Users/akihiroito/personalwork/git/trillion-game-lab-{issue}/research/{theme}/...
  /Users/akihiroito/personalwork/git/trillion-game-lab-{issue}/proposals/{name}/...
  ```
- **Git 操作**: `-C` フラグで worktree を指定する
  ```bash
  git -C /Users/akihiroito/personalwork/git/trillion-game-lab-{issue} add .
  git -C /Users/akihiroito/personalwork/git/trillion-game-lab-{issue} commit -m "feat: ..."
  ```
- **PR 作成**: `--repo` フラグでリポジトリを指定する
  ```bash
  cd /Users/akihiroito/personalwork/git/trillion-game-lab-{issue}
  gh pr create --repo machina-gg/trillion-game-lab --title "feat: ..." --body "..."
  ```

## クリーンアップ

マージ後の worktree 削除は `/cleanup-worktrees` スキルで一括実行する。
個別削除する場合:

```bash
git -C /Users/akihiroito/personalwork/git/trillion-game-lab worktree remove \
  /Users/akihiroito/personalwork/git/trillion-game-lab-{issue-number}
```

## 制約

- Worktree 1 つ = ブランチ 1 つ（同じブランチを複数 worktree で使えない）
- Worktree 内でのブランチ切り替えは避ける（専用ブランチで作業する）
