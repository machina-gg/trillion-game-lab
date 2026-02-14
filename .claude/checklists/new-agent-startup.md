# エージェント起動チェックリスト

新しいエージェントを起動する前に確認すること。

## 起動前（PM が実行）

- [ ] タスクの規模・性質を確認した
- [ ] スコープ（何をどこまでやるか）を明確にした
- [ ] `.claude/settings.json` に Read, Write, Edit, Glob, Grep が allow されている
- [ ] Delegate モードが OFF（Shift+Tab で確認）
- [ ] エージェント定義ファイル（`.claude/agents/*.md`）が最新

## 起動パラメータ

```
Task ツール:
  subagent_type: "general-purpose"
  model: "sonnet"（コスト最適化。重要タスクは "opus" も検討）
  mode: "bypassPermissions"
  prompt: ".claude/agents/{role}.md を読み込み、その役割に従って行動すること。
           タスク: {タスク内容}
           完了後は自分で PR を作成すること。"
```

## ロール別の起動判断

| 状況 | 起動するエージェント |
|------|-------------------|
| 新テーマのリサーチが必要 | **Researcher** |
| リサーチ結果から企画書作成 | **Planner** |
| 企画書の PR レビュー | **Editor** |
| リサーチの追加調査 | **Researcher** |
| 企画書の修正 | **Planner** |
| ファクトチェック | **Editor** |

## 起動後

- [ ] エージェントがツールを使用できることを確認
- [ ] タスクが正しく割り当てられていることを確認

## トラブルシューティング

| 症状 | 対処 |
|------|------|
| 「ツールがない」と報告 | Delegate モード解除 → 再起動 |
| タスクツールしか使えない | シャットダウン → 通常モードで再起動 |
| WebSearch/WebFetch が使えない | settings.json の権限を確認 |
