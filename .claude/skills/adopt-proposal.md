---
name: adopt-proposal
description: 採用された企画書を開発部（trillion-game）にハンドオフするスキル。PM が判定時に使用。
---

# 企画採用（Adopt Proposal）

## 概要

PM が企画書を「採用」と判定した場合、開発部（trillion-game リポ）に Issue を作成してハンドオフする。

## 手順

### Step 1: 企画書の最終確認

- Editor の APPROVE を確認する（`gh pr reviews` で確認）
- proposal.md の内容を最終レビューする
- review-notes.md の改善点が全て対応済みか確認する

```bash
# PR のレビューステータスを確認
gh pr view {PR番号} --repo machina-gg/trillion-game-lab --json reviews
```

### Step 2: 開発部に Issue 作成

```bash
gh issue create --repo machina-gg/trillion-game \
  --title "feat: {プロダクト名}" \
  --label "proposal,from-trillion-game-lab" \
  --body "$(cat <<'EOF'
## 企画書サマリー
{エレベーターピッチ}

## コンセプト
{コンセプト概要: 誰の・何の課題を・どう解決するか}

## 差別化ポイント
{競合との違い。なぜ既存プロダクトではダメか}

## 機能一覧（MVP）
- [ ] {機能 1}: {説明}
- [ ] {機能 2}: {説明}
- [ ] {機能 3}: {説明}
- [ ] {機能 4}: {説明}
- [ ] {機能 5}: {説明}

## 市場規模
| 指標 | 値 |
|------|-----|
| TAM | ${N}B |
| SAM | ${N}B |
| SOM | ${N}M |
| CAGR | {N}% |

## ビジネスモデル
{収益化の方法}

## 技術概要
{推奨技術スタック}

## 企画書リンク
- 企画書: https://github.com/machina-gg/trillion-game-lab/blob/develop/proposals/{name}/proposal.md
- リサーチ: https://github.com/machina-gg/trillion-game-lab/tree/develop/research/{theme}
- レビューノート: https://github.com/machina-gg/trillion-game-lab/blob/develop/proposals/{name}/review-notes.md

## From
プロダクト企画部（trillion-game-lab）より
EOF
)"
```

### Step 3: 記録

1. Issue URL を PR にコメントとして記録する

```bash
gh pr comment {PR番号} --repo machina-gg/trillion-game-lab \
  --body "開発部に Issue を作成しました: {Issue URL}"
```

2. proposals/{name}/proposal.md のステータスを `approved` に更新する

```
## ステータス
approved
```

3. 進捗管理を更新する（emit-event.sh を使用）

## チェックリスト

- [ ] Editor の APPROVE を確認した
- [ ] proposal.md の全セクションが完成している
- [ ] review-notes.md の改善点が全て対応済み
- [ ] `gh issue create --repo machina-gg/trillion-game` で Issue を作成した
- [ ] Issue URL を PR にコメントした
- [ ] proposal.md のステータスを `approved` に更新した
- [ ] 進捗管理を更新した

## 注意事項

- **企画書全文をコピーしない**: Issue にはサマリーを記載し、詳細はリンクで参照する
- **開発部 PM が Issue を受け取り、タスク分解する**: 企画部は実装に介入しない
- **リサーチデータへのアクセス**: 開発部が必要に応じて企画部のリサーチを参照できるよう、リンクを必ず含める
