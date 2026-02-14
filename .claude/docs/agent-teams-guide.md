# Agent Teams 運用ガイド

## フラット構造

```
PM（常駐・薄いルーター）
├── Researcher（市場・競合リサーチ）
├── Planner（企画書作成）
└── Editor（レビュー・品質管理）
```

- PM がエージェントを直接起動してタスクを委譲する
- エージェントは Worktree で自律的に作業し、自分で PR を作成する

## タスクの End-to-End フロー

1. PM が Issue 作成・サイズ判定
2. PM が `/delegate-task` でエージェントを起動（Worktree 必須）
3. エージェントが Worktree で作業 → PR 作成
4. PM がレビュアー（Editor）を起動（`/delegate-task` Step 2）
5. レビュー通過 → PM がマージ
6. Worktree クリーンアップ（`/cleanup-worktrees`）
7. 振り返りチェック

詳細手順: `.claude/skills/delegate-task.md`

## PM → エージェント の起動手順

### 1. 起動前チェックリスト

- [ ] `.claude/settings.json` に Read, Write, Edit, Glob, Grep が allow されている
- [ ] Delegate モードが OFF になっている（Shift+Tab で確認）
- [ ] タスクのスコープ（何をどこまでやるか）が明確

### 2. エージェント起動テンプレート

```
Task ツールで起動:
  subagent_type: "general-purpose"
  model: "sonnet"（コスト最適化。重要タスクは "opus" も検討）
  mode: "bypassPermissions"
  prompt: ".claude/agents/{role}.md を読み込み、その役割に従って行動すること。
           タスク: {タスク内容}
           Worktree を作成してから作業を開始すること。
           完了後は自分で PR を作成すること。"
```

### 3. レビュアー起動テンプレート

```
Task ツールで起動:
  subagent_type: "general-purpose"
  model: "sonnet"
  mode: "bypassPermissions"
  prompt: ".claude/agents/editor.md を読み込み、/review-pr {PR番号} を実行すること。
           レビュー完了後は gh pr review で結果を投稿すること。"
```

| 変更内容 | レビュアー |
|---------|-----------|
| リサーチ成果物 | Editor |
| 企画書 | Editor |
| 運営変更 | PM 自身 |

### 4. エージェントに伝えること

- 担当タスク（Issue 番号・内容）
- 関連するリサーチ・企画書の場所
- 制約事項（テーマの範囲、期限等）
- ファイルパス（絶対パス）

### 5. エージェントがツール権限不足を報告した場合

- Delegate モードを解除（Shift+Tab）
- エージェントをシャットダウン
- 通常モードで再起動
- **PM が自分で作業しない**（ロール違反）

## エージェント起動の判断基準

| 状況 | 起動するエージェント |
|------|-------------------|
| 新テーマのリサーチ開始 | Researcher |
| リサーチ完了 → 企画書作成 | Planner |
| 企画書の PR レビュー | Editor |
| 追加調査が必要 | Researcher |
| 企画書の修正 | Planner |
| リサーチのファクトチェック | Editor |

## エージェントの自律行動

各エージェントは以下をセルフサービスで実行する（PM の指示不要）:

| 行動 | 実行者 |
|------|--------|
| Worktree 作成（必須） | 全エージェント |
| PR 作成 | Researcher / Planner |
| エージェント間の直接通信 | 全エージェント（Researcher ↔ Planner、Planner ↔ Editor 等） |

## トラブルシューティング

| 症状 | 原因 | 対処 |
|------|------|------|
| エージェントが「ツールがない」と報告 | Delegate モード or settings.json の権限不足 | Shift+Tab でモード解除 → 再起動 |
| エージェントがタスクツールしか使えない | Delegate モードで起動した | シャットダウン → 通常モードで再起動 |
| WebSearch が使えない | 権限不足 | settings.json を確認 |
| リサーチデータが古い | ソースが古い | Researcher に再調査を指示 |
