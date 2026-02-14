# 部署間連携ガイド

## 企画部 → 開発部

### トリガー

PM が企画書を「採用（adopt）」と判定した時。

### 手順

1. `/adopt-proposal` スキルを実行
2. `gh issue create --repo machina-gg/trillion-game` で Issue 作成
3. ラベル: `proposal`, `from-trillion-game-lab`
4. Issue 本文に企画書サマリー、コンセプト、差別化、MVP機能、市場規模、リンクを記載

### Issue 本文に含める情報

| セクション | 内容 |
|-----------|------|
| 企画書サマリー | エレベーターピッチ |
| コンセプト | 誰の・何の課題を・どう解決するか |
| 差別化ポイント | 競合との違い |
| 機能一覧（MVP） | 3-5機能のチェックリスト |
| 市場規模 | TAM/SAM/SOM/CAGR |
| ビジネスモデル | 収益化の方法 |
| 企画書リンク | proposal.md, research/ へのリンク |

### 注意

- 企画書全文をコピーしない（リンクで参照）
- 開発部 PM が Issue を受け取り、タスク分解する
- 企画部は実装に介入しない

## 開発部 → 企画部

### トリガー

開発部で追加調査が必要になった時。

### 手順

1. `gh issue create --repo machina-gg/trillion-game-lab` で Issue 作成
2. ラベル: `from-trillion-game`
3. 何を調査してほしいかを明記

### Issue 本文に含める情報

| セクション | 内容 |
|-----------|------|
| 背景 | なぜ追加調査が必要か |
| 調査依頼 | 何を調べてほしいか（具体的に） |
| 期待する成果物 | どんな形式で欲しいか |
| 関連 Issue | 開発部側の Issue へのリンク |

### 注意

- 企画部 PM が Issue を受け取り、Researcher を起動
- 調査結果は research/ に追加し、PR で共有
- 開発部からの Issue には `from-trillion-game` ラベルを付与して識別する

## 連携フロー図

```
企画部（trillion-game-lab）          開発部（trillion-game）
  │                                    │
  ├─ リサーチ                           │
  ├─ 企画書作成                         │
  ├─ レビュー・承認                     │
  │                                    │
  ├─ /adopt-proposal ─────────────→ Issue 受付
  │   (Issue 作成)                     ├─ タスク分解
  │                                    ├─ 設計
  │                                    ├─ 実装
  │                                    ├─ テスト
  │                                    ├─ リリース
  │                                    │
  │  ← Issue 作成（追加調査依頼）──────┤
  ├─ 追加リサーチ                       │
  ├─ 結果共有（PR）                    │
  │                                    │
```

## ラベル体系

| ラベル | リポジトリ | 意味 |
|-------|-----------|------|
| `proposal` | trillion-game | 企画部から採用された企画 |
| `from-trillion-game-lab` | trillion-game | 企画部からのハンドオフ |
| `from-trillion-game` | trillion-game-lab | 開発部からの調査依頼 |
