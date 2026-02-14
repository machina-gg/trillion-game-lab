---
name: delegate-task
description: タスク委譲スキル（End-to-End）。Issue 起点 → Worktree 作業 → レビュー → マージ → 振り返りまで一気通貫。
---

# タスク委譲（End-to-End 5ステップ）

## ユーザー依頼スコープの完遂（必須）

ユーザーから複数 Issue をまとめて依頼された場合、**全 Issue の完了まで止まらず進める**。

```
OK: 「#20, #21, #22 をやりたい」→ 3件全て完了してから報告
NG: #20, #21 を完了した時点で「次は #22 に進めます。他に指示はありますか？」と聞く
```

**途中で確認を挟んでよいケース:**
- 依頼のスコープが曖昧で判断できない場合
- 権限不足で作業が止まった場合（権限報告 → ユーザー承認待ち）
- 依頼内容と矛盾する問題が発生した場合

**途中で確認を挟んではいけないケース:**
- 依頼スコープが明確で、残りの Issue がある場合
- CI 修正など技術的な問題は自力で解決して進める

## 複数タスク委譲時の並行実行（必須）

複数の Issue を同時に委譲する場合は、**並行実行をデフォルト**とする。

```
OK: 3件の Issue → Researcher 3体を同時起動（各自 Worktree で独立作業）
NG: 3件の Issue → 1件ずつ順番に完了を待ってから次に進む
```

**手順:**
1. エージェントを Issue 数だけ並行起動（run_in_background: true）
2. 完了した PR から順にレビュー → マージ（同一ファイル変更の場合はリベースで対応）

**同一ファイル変更でも並行実行する。** Worktree は独立しているため競合しない。マージ時のコンフリクトは後続 PR がリベースして解消する。

## 手順（5ステップ）

### Step 0: タスク確認

タスクを開始する前に確認すること:
- Issue が作成されていること
- タスクサイズが判定されていること
- 対象リポジトリが明確になっていること

### Step 1: エージェント起動（Worktree 必須）
```
Task ツール:
  subagent_type: "general-purpose"
  model: "sonnet"（重要タスクは "opus"）
  mode: "bypassPermissions"
  run_in_background: true（並行作業時）
  prompt: ".claude/agents/{role}.md を読み込み、その役割に従って行動すること。
           タスク: {タスク内容}
           Worktree を作成してから作業を開始すること。
           git -C /Users/akihiroito/personalwork/git/trillion-game-lab worktree add /Users/akihiroito/personalwork/git/trillion-game-lab-{issue} -b 'feature/{issue}-{desc}' origin/develop
           完了後は自分で PR を作成し、PM に報告すること。
           PR 本文に必ず 'Closes #{issue番号}' を含めること。"
```

### Step 2: レビュー（必須・省略禁止）

PM が変更内容に応じたレビュアーを起動する:

| 変更内容 | レビュアー |
|---------|-----------|
| リサーチ成果物（market-analysis, trend-report 等） | **Editor** |
| 企画書（proposal.md 等） | **Editor** |
| 運営変更（CLAUDE.md、ルール、スキル、ワークフロー） | **PM 自身** |

レビュアーの起動方法:
```
Task ツール:
  subagent_type: "general-purpose"
  model: "sonnet"
  mode: "bypassPermissions"
  prompt: ".claude/agents/{role}.md を読み込み、/review-pr {PR番号} を実行すること。
           レビュー完了後は gh pr review で結果を投稿すること。"
```

結果による分岐:
- **APPROVE** → Step 3 に進む
- **REQUEST_CHANGES** → 修正エージェントを再起動 → 修正後 Step 2 に戻る

### Step 3: マージ + クリーンアップ

```bash
# CI 通過を確認（必須。CI 未通過でのマージは禁止）
gh pr checks {PR番号} --repo machina-gg/trillion-game-lab
# 全チェックが pass であることを確認してからマージする

# Merge commit（コミット履歴を保持）
gh pr merge {PR番号} --merge

# Worktree クリーンアップ（マージ済みブランチを一括削除）
# /cleanup-worktrees スキルを実行
```

### Step 4: 振り返りチェック

振り返りチェック:
1. `/retrospective` スキルを実行して振り返りを実施する（**省略禁止**）
2. Phase の全タスクが完了なら:
   - `/release-automation` スキルでリリース処理を実施

## タスクサイズと起動判断

| サイズ | Step 1（起動） | Step 2（レビュー） |
|--------|---------------|-------------------|
| **S** (1ファイル) | Researcher or Planner のみ | Editor レビュー |
| **M** (2-5ファイル) | Researcher + Planner（並行可） | Editor レビュー |
| **L** (6+ファイル) | Researcher → Planner（リサーチ後に企画） | Editor が全成果物をレビュー |

## 自動化されている部分

- **Worktree**: エージェントのセルフサービス（`.claude/skills/worktree-setup.md`）
- **PR 作成**: エージェントが自分で `gh pr create` を実行する
