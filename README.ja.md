[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🚀 Awesome MCP Servers

**Cursor、Claude Code、Kimi CodeのためのMCPエコシステム。設定ファイルひとつで、真のスーパーパワーを。**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servers)

<br/>

[MCPとは？](#mcpとは) • [サーバー一覧](#サーバー一覧) • [クイックスタート](#クイックスタート) • [カテゴリ](#カテゴリ) • [FAQ](#faq) • [コントリビュート](CONTRIBUTING.md)

</div>

---

## MCPとは？

**モデルコンテキストプロトコル（Model Context Protocol、MCP）** は、AIコーディングアシスタントが外部ツール、データベース、サービスに接続するためのオープンスタンダードです。AIが孤立して作業する代わりに、MCPはスーパーパワーを付与します。データベースへのクエリ、リポジトリの管理、ウェブブラウジングなどが可能になります。

---

## Before / After

<table>
<tr>
<td width="50%" valign="top">

### ❌ MCPなし

```
You: "Check our Postgres for the user count"
AI:  "I can't access your database."

You: "Look at the latest issues on GitHub"
AI:  "I don't have access to GitHub."

You: "What does the React docs say about hooks?"
AI:  "My training data may be outdated."
```

</td>
<td width="50%" valign="top">

### ✅ MCPあり

```
You: "Check our Postgres for the user count"
AI:  → Queries your DB → "You have 14,832 users."

You: "Look at the latest issues on GitHub"
AI:  → Reads issues → "3 open bugs, 2 feature requests."

You: "What does the React docs say about hooks?"
AI:  → Fetches live docs → "Here's the latest API..."
```

</td>
</tr>
</table>

**MCPはAIをスマートなオートコンプリートからフルスタックのエンジニアリングチームメイトへと変貌させます。**

---

## サーバー一覧

| # | サーバー | カテゴリ | 説明 | パッケージ |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 ファイル | ローカルファイルの読み書きと管理 | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 開発 | リポジトリ、Issues、PR、コード検索 | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ データベース | PostgreSQLデータベースのクエリと探索 | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ データベース | キャッシュ、Pub/Sub、キーバリュー操作 | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 Web | BraveまたはGoogleでウェブ検索 | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 ナレッジ | 永続メモリとナレッジグラフ | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 Web | ブラウザ自動化とウェブスクレイピング | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 コミュニケーション | メッセージ送信とチャンネル管理 | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 ドキュメント | 最新のライブラリドキュメント | `@upstash/context7-mcp` |

---

## カテゴリ

| カテゴリ | サーバー | 説明 |
|----------|---------|-------------|
| [🔧 開発](by-category/development.md) | GitHub | コード、リポジトリ |
| [🗄️ データベース](by-category/databases.md) | PostgreSQL, Redis | クエリ、ストレージ、キャッシュ |
| [💬 コミュニケーション](by-category/communication.md) | Slack | メッセージング |
| 📁 ファイル | Filesystem | ローカルファイル操作 |
| 🌐 Web | Web Search, Puppeteer | 検索、ブラウザ自動化 |
| 🧠 ナレッジ | Memory, Context7 | 永続コンテキスト、ライブドキュメント |

---

## クイックスタート

30秒以内にMCPサーバーをAIコーディングアシスタントに追加できます。

### Cursor

1. プロジェクトルートに `.cursor/mcp.json` を作成または編集：

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
    }
  }
}
```

2. Cursorを再起動。ステータスバーにMCPサーバーアイコンが表示されます。

### Claude Code

```bash
# 1コマンドでサーバーを追加
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# 動作確認
claude mcp list
```

### Kimi Code

Kimi Codeの設定ディレクトリにある `config.toml` で設定：

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## 複数サーバーの同時利用

必要な数だけサーバーを追加できます：

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "."]
    },
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_xxxxxxxxxxxx"
      }
    },
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://localhost/mydb"]
    }
  }
}
```

---

## FAQ

<details>
<summary><strong>MCPとは何ですか？</strong></summary>

モデルコンテキストプロトコル（Model Context Protocol、MCP）は、Anthropicが作成したオープンスタンダードで、AIアシスタントが外部ツールやデータソースに接続する方法を定義します。AIのためのユニバーサルアダプターと考えてください。1つのプロトコルで任意のツールに接続できます。

</details>

<details>
<summary><strong>MCPは無料ですか？</strong></summary>

はい。MCP自体はオープンプロトコル（MITライセンス）です。各MCPサーバーはローカルで無料実行できます。一部はサードパーティサービスのAPIキーが必要な場合があります（GitHubトークン、Slackトークンなど）。

</details>

<details>
<summary><strong>どのAIアシスタントがMCPをサポートしていますか？</strong></summary>

2026年時点で、MCPをサポートするアシスタントは以下の通りです：
- **Cursor** — `.cursor/mcp.json` で完全サポート
- **Claude Code** — CLI（`claude mcp add`）で完全サポート
- **Kimi Code** — `AGENTS.md` または `config.toml` で完全サポート
- **Windsurf**、**Cline**、**Continue** — サポート拡大中

</details>

<details>
<summary><strong>MCPサーバーは安全ですか？</strong></summary>

MCPサーバーはあなたのマシン上でローカルに実行されます。付与した権限のみを持ちます。追加前にサーバーの機能を確認してください。本番環境ではファイルパスを制限し、可能な限り読み取り専用データベース接続を使用してください。

</details>

<details>
<summary><strong>独自のMCPサーバーを構築できますか？</strong></summary>

もちろんです。MCP SDKは[TypeScript](https://github.com/modelcontextprotocol/typescript-sdk)と[Python](https://github.com/modelcontextprotocol/python-sdk)で利用可能です。詳細は[公式ドキュメント](https://modelcontextprotocol.io)をご覧ください。

</details>

<details>
<summary><strong>サーバーが動作しない場合のトラブルシューティング方法は？</strong></summary>

1. Node.js 18+（または必要なランタイム）がインストールされていることを確認
2. ターミナルでコマンドを手動実行してエラーを確認
3. 必要な環境変数/APIキーが設定されているか確認
4. MCP設定変更後にAIアシスタントを再起動

</details>

---

## 関連プロジェクト

| プロジェクト | 説明 |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 本番環境対応の20のAIコーディングルール |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — プロジェクトのAI対応度をスコアリング |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — AIがコミットメッセージを作成 |

## コントリビュート

コントリビューションを大歓迎します！新しいMCPサーバーの追加方法は [CONTRIBUTING.md](CONTRIBUTING.md) をご覧ください。

---

## ライセンス

[MIT](LICENSE) — 自由にお使いください。

---

<div align="center">

**MCPコミュニティが ❤️ を込めて構築しました**

[⬆ トップに戻る](#-awesome-mcp-servers)

</div>

---
