# my-json-server

## Overview

JSON Serverを使用した簡易モックAPIサーバー。項目定義グループと定義データを管理するためのRESTful APIを提供します。

## Tech Stack

- [JSON Server](https://github.com/typicode/json-server) / [My JSON Server](https://my-json-server.typicode.com/)
- RESTful API

## Setup

### ローカルでJSON Serverを使用する場合

```bash
# JSON Serverをインストール
npm install -g json-server

# サーバーを起動
json-server --watch db.json
```

### GitHub経由でMy JSON Serverを使用する場合

以下のURLでアクセス可能：

```
https://my-json-server.typicode.com/{username}/my-json-server
```

## Usage

### 利用可能なエンドポイント

- `GET /definition_groups` - 全ての項目定義グループを取得
- `GET /definition_groups/:id` - 特定の項目定義グループを取得
- `GET /definitions` - 全ての定義を取得
- `GET /definitions/:id` - 特定の定義を取得

### データ構造

**definition_groups**: 項目グループと配下の項目を管理
- `id`: グループID
- `name`: グループ名（例: "項目グループ1"）
- `items`: 項目の配列
  - `id`: 項目ID
  - `name`: 項目名（例: "項目1-1"）

## Directory Structure

```
.
├── README.md       # プロジェクトドキュメント
└── db.json         # JSONデータベースファイル
```

## License

This repository is for personal/private use only.
