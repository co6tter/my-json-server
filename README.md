# my-json-server

## Overview

JSON Serverを利用した簡易モックAPIサーバーです。項目定義グループ（`definition_groups`）と定義データ（`definitions`）を管理するRESTful APIを提供します。My JSON Serverを使えばGitHubリポジトリを公開するだけでAPIとして利用可能なため、フロントエンド開発時のモックバックエンドとして活用できます。

## Tech Stack

- [JSON Server](https://github.com/typicode/json-server) — JSONファイルをREST APIとして公開するツール
- [My JSON Server](https://my-json-server.typicode.com/) — GitHubリポジトリのdb.jsonをホスティングするサービス

## Prerequisites

ローカルで動かす場合のみ以下が必要です。

- Node.js（LTS推奨）
- json-server（グローバルインストール）

## Setup

### ローカル環境で動かす場合

```bash
# json-serverをグローバルインストール
npm install -g json-server

# サーバーを起動（デフォルトポート: 3000）
json-server --watch db.json
```

### My JSON Server（GitHub経由）を使う場合

このリポジトリをGitHubにpushするだけで、以下のURLで自動的にAPIが公開されます。インストール不要です。

```
https://my-json-server.typicode.com/co6tter/my-json-server
```

## Usage

### エンドポイント一覧

| メソッド | パス | 説明 |
|---|---|---|
| `GET` | `/definition_groups` | 全ての項目定義グループを取得 |
| `GET` | `/definition_groups/:id` | 指定IDの項目定義グループを取得 |
| `GET` | `/definitions` | 全ての定義を取得 |
| `GET` | `/definitions/:id` | 指定IDの定義を取得 |

### リクエスト例

```bash
# 全グループ取得
curl https://my-json-server.typicode.com/co6tter/my-json-server/definition_groups

# ID=1のグループを取得
curl https://my-json-server.typicode.com/co6tter/my-json-server/definition_groups/1
```

### データ構造

**definition_groups**

```json
{
  "id": 1,
  "name": "その他グループ",
  "items": [
    { "id": 1, "name": "取り込まない項目" },
    { "id": 2, "name": "職員番号" }
  ]
}
```

**definitions**

現在データなし。`db.json` に追加することで拡張可能。

## Directory Structure

```
.
├── db.json     # APIのデータソース（JSONデータベース）
└── README.md   # プロジェクトドキュメント
```

## License

MIT
