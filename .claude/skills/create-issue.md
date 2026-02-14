---
name: create-issue
description: GitHub Issue 作成の標準手順。PM が要件をスコープ定義する時に使用。
---

# GitHub Issue 作成

## 概要

PM がユーザー要件を受け取った後、GitHub Issue を作成してタスクのスコープを定義する。
Issue 作成後、必要に応じてエージェントにタスクを委譲する。

## Issue 作成コマンド

```bash
gh issue create \
  --repo machina-gg/trillion-game-lab \
  --title "feat: {タスクの概要}" \
  --body "$(cat <<'EOF'
## 概要
{何を実現するか}

## 背景
{なぜ必要か}

## 要件
- [ ] {具体的な要件 1}
- [ ] {具体的な要件 2}
- [ ] {具体的な要件 3}

## 対象
`research/{theme}` or `proposals/{name}`

## 備考
{制約条件、参考情報}
EOF
)"
```

## タイトル規約

| プレフィックス | 用途 | 例 |
|-------------|------|-----|
| `feat:` | 新規リサーチ・企画 | `feat: SaaS ダッシュボード市場リサーチ` |
| `fix:` | 修正 | `fix: 競合分析のデータ更新` |
| `docs:` | ドキュメント | `docs: リサーチテンプレートの改善` |
| `refactor:` | リファクタリング | `refactor: 企画書フォーマットの見直し` |
| `chore:` | 設定・CI | `chore: CI にリンクチェック追加` |

## Issue 作成後のフロー

1. **Issue 作成**: PM が `gh issue create` で作成
2. **タスク分解**: PM がタスクサイズを判定（`.claude/checklists/task-decomposition.md` 参照）
3. **エージェント起動**: PM が `/delegate-task` でエージェントを起動
4. **PR 紐付け**: エージェントが PR を作成する際に `Closes #{issue-number}` で紐付け

## ラベル規約

| ラベル | 用途 |
|-------|------|
| `research` | リサーチタスク |
| `proposal` | 企画書タスク |
| `review` | レビュータスク |
| `improvement` | 改善提案 |
| `from-trillion-game` | 開発部からの依頼 |

## 注意事項

- **1 Issue = 1 PR** を基本とする（CLAUDE.md ルール参照）
- 大きな変更は複数の Issue に分解する
- Issue 番号はブランチ名に含める（`feature/{issue-number}-description`）
