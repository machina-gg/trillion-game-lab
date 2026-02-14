---
name: retrospective
description: サイクル完了時の振り返りスキル。Good/Bad/Improvements を実施し、改善点を Issue 化して次サイクルに回す。
---

# 振り返り（Retrospective）

## 概要

リサーチ・企画サイクル（1つ以上の Issue 完了）後に PM が実施する。
発見された改善点は **必ず Issue 化** して次のサイクルに回す。
振り返りして終わりにしない。Issue を作って初めて完了。

## 実施タイミング

- delegate-task の Step 4 完了後
- 複数 Issue を並行処理した場合はまとめて1回実施
- Phase の全タスク完了時（リリース前）

## 手順（4ステップ）

### Step 1: 事実の収集

今回のサイクルで起きたことを列挙する:

```
- 実施した Issue: #{N}, #{N}, ...
- 関与したエージェント: Researcher, Planner, Editor, ...
- レビューで検出された問題: {件数}
- CI 失敗: {件数}
- ブロッカー: {あれば記述}
```

### Step 2: Good / Bad / Improvements の分類

| 分類 | 観点 | 記入 |
|------|------|------|
| **Good** | うまくいったこと。継続すべきこと | {記入} |
| **Bad** | 問題が起きたこと。再発防止が必要なこと | {記入} |
| **Improvements** | まだ問題ではないが改善できること | {記入} |

### Step 3: 改善点の Issue 化（必須）

Bad と Improvements の各項目について、以下を判定する:

| 判定 | 条件 | アクション |
|------|------|----------|
| **Issue 化する** | 仕組みの変更が必要（スキル、CI、自動化 etc.） | `gh issue create` で Issue 作成 |
| **ルール反映する** | 運用ルールの追加・修正で対応可能 | CLAUDE.md / スキル / チェックリストに反映 |
| **記録のみ** | 一時的な問題で再発リスクが低い | コメントとして記録して終了 |

**Issue 作成テンプレート:**

```bash
gh issue create \
  --repo machina-gg/trillion-game-lab \
  --title "{prefix}: {改善内容}" \
  --label "improvement" \
  --body "$(cat <<'EOF'
## 背景
振り返り（{日付}）で発見された改善点。

## 発見時の状況
{どの Issue / PR の作業中に発見されたか}

## 問題
{何が問題だったか}

## 提案する改善
{どう改善すべきか}

## 対象
{変更が必要なファイル/仕組み}
EOF
)"
```

### Step 4: 振り返り結果の報告

振り返り完了後、以下をユーザーに報告する:
- Good={件数}
- Bad={件数}
- Improvements={件数}
- Issue作成={件数}

## チェックリスト（実施確認）

- [ ] Step 1: 事実を収集した
- [ ] Step 2: Good/Bad/Improvements に分類した
- [ ] Step 3: Bad/Improvements の全項目について Issue化 / ルール反映 / 記録のみ を判定した
- [ ] Step 3: Issue 化が必要なものは `gh issue create` で作成した
- [ ] Step 3: ルール反映が必要なものは該当ファイルを更新した
- [ ] Step 4: 振り返り結果を報告した

## 注意事項

- **「次やる」は禁止**: 改善点を見つけたらその場で Issue を作る。「後で」は忘れる
- **Issue の粒度**: 1改善点 = 1 Issue。複合的なものは分割する
- **Good も記録する**: 良かったことの継続もチームの資産
