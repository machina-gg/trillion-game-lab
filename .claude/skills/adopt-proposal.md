---
name: adopt-proposal
description: proposals/adopted/ から採用済み企画書を読み取り、開発部に Issue を作成するスキル。
---

# 企画書の開発部提案（Adopt Proposal）

## 概要

ダッシュボードで「adopted」と判定された企画書を、開発部（machina-gg/trillion-game）に Issue として送る。

## 前提条件

- `sort-proposals` スキルで振り分け済みであること
- 対象の企画書が `proposals/adopted/{slug}/proposal.md` に存在すること

## 手順

### Step 1: 採用済み提案の確認

```bash
ls proposals/adopted/
```

各 `proposals/adopted/{slug}/` をチェックし、proposal.md の Status が `approved`（開発部に送付済み）でないものを対象にする。

### Step 2: 企画書の読み込み

対象の `proposals/adopted/{slug}/proposal.md` を読み込み、以下を抽出:

- エレベーターピッチ
- コンセプト
- 差別化ポイント
- MVP 機能一覧
- 市場規模（TAM/SAM/SOM/CAGR）
- ビジネスモデル
- 技術概要

### Step 3: 開発部に Issue 作成

```bash
gh issue create --repo machina-gg/trillion-game \
  --title "feat: {プロダクト名}" \
  --label "proposal,from-trillion-game-lab" \
  --body "$(cat <<'EOF'
## 提案概要
{エレベーターピッチ}

## コンセプト
{コンセプト概要}

## 差別化
{競合との差}

## MVP 機能
- [ ] {機能 1}
- [ ] {機能 2}
- [ ] {機能 3}

## 市場規模
TAM: ${N}B
SAM: ${N}B
SOM: ${N}M
CAGR: {N}%

## ビジネスモデル
{収益化方法}

## 技術概要
{推奨技術スタック}

## 企画書リンク
- 企画書: https://github.com/machina-gg/trillion-game-lab/blob/develop/proposals/adopted/{slug}/proposal.md
- リサーチ: https://github.com/machina-gg/trillion-game-lab/tree/develop/research/{theme}

## From
プロダクト企画部（trillion-game-lab）
EOF
)"
```

### Step 4: ステータス更新

proposal.md の Status を `approved` に更新する。

### Step 5: 完了報告

- 開発部に送付した提案: {N} 件
- Issue URL: {各 Issue の URL}

## チェックリスト

- [ ] proposals/adopted/ に対象の提案がある
- [ ] proposal.md の全セクションが揃っている
- [ ] 開発部に Issue を作成した
- [ ] Issue に `proposal` + `from-trillion-game-lab` ラベルを付けた
- [ ] proposal.md の Status を `approved` に更新した
