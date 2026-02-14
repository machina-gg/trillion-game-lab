# Trillion Game Lab - プロダクト企画部

ブルーオーシャン市場のリサーチ・トレンド分析・プロダクト企画書の量産を行うリポジトリです。

## ミッション

月額 $250 以下で、兆ドル規模のプロダクトを生み出す。

## 組織構成

```
PM（常駐・薄いルーター）
├── Researcher（市場調査・トレンド分析）
├── Planner（企画書作成）
└── Editor（品質レビュー・校正）
```

| 役割 | 責任範囲 |
|------|---------|
| PM | テーマ選定、Issue 作成、エージェント起動、採用/保留/却下の判定、開発部へのハンドオフ |
| Researcher | WebSearch/WebFetch でデータ収集、市場分析・トレンド・競合分析の文書化 |
| Planner | リサーチを元に企画書（コンセプト・差別化・機能一覧）を作成 |
| Editor | 企画書の論理性・完全性・データ裏付けをレビュー |

## ワークフロー

```
Phase 1: テーマ選定（PM） → Issue 作成
Phase 2: リサーチ（Researcher） → research/{theme}/ に成果物
Phase 3: 企画書作成（Planner） → proposals/{name}/ に企画書
Phase 4: レビュー（Editor） → review-notes.md にフィードバック
Phase 5: 判定（PM） → adopt / hold / reject
```

採用された企画は開発部（[trillion-game](https://github.com/machina-gg/trillion-game)）に Issue としてハンドオフされます。

## ディレクトリ構成

```
trillion-game-lab/
├── CLAUDE.md           ← 社訓・ルール定義
├── .claude/            ← エージェント設定
├── .github/            ← CI・Issue テンプレート
├── research/           ← Researcher の成果物
│   └── {theme-slug}/
│       ├── market-analysis.md
│       ├── trend-report.md
│       ├── competitor-analysis.md
│       └── sources.md
├── proposals/          ← Planner の成果物（ライフサイクル管理）
│   ├── inbox/          ← 新規・レビュー中の提案
│   │   └── {proposal-slug}/
│   │       ├── proposal.md
│   │       ├── research-ref.md
│   │       └── review-notes.md
│   ├── adopted/        ← 採用済み
│   ├── rejected/       ← 不採用
│   └── on-hold/        ← 保留
├── templates/          ← テンプレート
└── README.md
```

## ブランチ戦略

- `main` - 本番リリース用
- `develop` - 開発統合ブランチ
- `feature/{issue-number}-{description}` - 機能開発
- `hotfix/{issue-number}-{description}` - 緊急修正

## 部署間連携

| 方向 | 方法 |
|------|------|
| 企画部 → 開発部 | `/adopt-proposal` で `machina-gg/trillion-game` に Issue 作成 |
| 開発部 → 企画部 | `machina-gg/trillion-game-lab` に Issue 作成（追加調査依頼） |

## 詳細

全てのルール・ワークフローの詳細は [CLAUDE.md](./CLAUDE.md) を参照してください。
