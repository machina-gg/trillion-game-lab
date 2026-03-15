# Trillion Game Lab — 企画書保管庫

プロダクト企画部の成果物（企画書・レビューノート・テンプレート・レポート）を保管するリポジトリ。
エージェント定義・スキル・ルールは本部リポ（`machina-gg/trillion-game`）に集約されている。

## ディレクトリ構成

```
proposals/
├── inbox/       ← 新規・レビュー中の提案
├── adopted/     ← 採用済み（開発部へハンドオフ対象）
├── rejected/    ← 不採用
└── on-hold/     ← 保留（追加調査待ち）
templates/       ← 企画書テンプレート
```

## 操作元

このリポのデータは `trillion-game` リポの企画部スキルから操作される:
- 企画書作成: `.claude/skills/write-proposal.md`
- レビュー: `.claude/skills/review-proposal.md`
- ダッシュボード: `.claude/skills/generate-dashboard.md`
- 振り分け: `.claude/skills/sort-proposals.md`
- 開発部への提案: `.claude/skills/adopt-proposal.md`

## ルール

- Worktree 配置: `/Users/akihiroito/personalwork/git/trillion-game-lab-{issue-number}/`
- Git Flow: main → feature/* → PR → main
