[English](README.md)

<div align="center">

# 🚀 Awesome MCP Servers — 中文版

**面向 Cursor、Claude Code 和 Kimi Code 的 MCP 生态。一个配置文件，真正的超能力。**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servers)

<br/>

[什么是 MCP？](#什么是-mcp) • [服务器列表](#服务器列表) • [快速开始](#快速开始) • [分类总览](#分类总览) • [常见问题](#常见问题) • [参与贡献](CONTRIBUTING.md)

</div>

---

## 什么是 MCP？

**模型上下文协议（Model Context Protocol，MCP）** 是一个开放标准，让 AI 编程助手能够连接外部工具、数据库和服务。MCP 赋予了 AI 超能力——它不再孤立工作，而是可以查询数据库、管理代码仓库、浏览网页，等等。

---

## 使用前后对比

<table>
<tr>
<td width="50%" valign="top">

### ❌ 没有 MCP

```
你："查一下我们的 Postgres 数据库里有多少用户"
AI："我无法访问你的数据库。"

你："看看 GitHub 上最新的 issues"
AI："我没有 GitHub 的访问权限。"

你："React 文档里 Hooks 怎么说的？"
AI："我的训练数据可能已经过时了。"
```

</td>
<td width="50%" valign="top">

### ✅ 使用 MCP

```
你："查一下我们的 Postgres 数据库里有多少用户"
AI：→ 查询数据库 → "共有 14,832 个用户。"

你："看看 GitHub 上最新的 issues"
AI：→ 读取 issues → "3 个未修复的 Bug，2 个功能请求。"

你："React 文档里 Hooks 怎么说的？"
AI：→ 获取最新文档 → "这是最新的 API 说明……"
```

</td>
</tr>
</table>

**MCP 让你的 AI 从一个智能补全工具，变成一个全栈工程队友。**

---

## 服务器列表

| # | 服务器 | 分类 | 说明 | 包名 |
|---|--------|------|------|------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 文件 | 读写和管理本地文件 | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 开发 | 仓库、Issues、PR 和代码搜索 | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ 数据库 | 查询和浏览 PostgreSQL 数据库 | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ 数据库 | 缓存、发布/订阅和键值操作 | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 网页 | 使用 Brave 或 Google 搜索网页 | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 知识 | 持久化记忆和知识图谱 | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 网页 | 浏览器自动化和网页抓取 | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 通讯 | 发送消息和管理频道 | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 文档 | 最新的库文档 | `@upstash/context7-mcp` |

---

## 分类总览

| 分类 | 服务器 | 说明 |
|------|--------|------|
| [🔧 开发](by-category/development.md) | GitHub | 代码、仓库 |
| [🗄️ 数据库](by-category/databases.md) | PostgreSQL, Redis | 查询、存储、缓存 |
| [💬 通讯](by-category/communication.md) | Slack | 消息收发 |
| 📁 文件 | Filesystem | 本地文件操作 |
| 🌐 网页 | Web Search, Puppeteer | 搜索、浏览器自动化 |
| 🧠 知识 | Memory, Context7 | 持久化上下文、实时文档 |

---

## 快速开始

30 秒内将 MCP 服务器添加到你的 AI 编程助手中。

### Cursor

1. 在项目根目录创建或编辑 `.cursor/mcp.json`：

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

2. 重启 Cursor。底部状态栏会出现 MCP 服务器图标。

### Claude Code

```bash
# 一条命令添加服务器
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# 验证是否运行成功
claude mcp list
```

### Kimi Code

在 Kimi Code 配置目录下的 `config.toml` 中进行配置：

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## 同时使用多个服务器

你可以按需叠加任意数量的服务器：

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

## 常见问题

<details>
<summary><strong>什么是 MCP？</strong></summary>

模型上下文协议（Model Context Protocol，MCP）是 Anthropic 创建的开放标准，定义了 AI 助手如何连接外部工具和数据源。可以把它理解为 AI 的万能适配器——一个协议，连接任意工具。

</details>

<details>
<summary><strong>MCP 是免费的吗？</strong></summary>

是的。MCP 本身是开放协议（MIT 许可）。各个 MCP 服务器可以免费在本地运行。部分服务器可能需要第三方服务的 API 密钥（如 GitHub Token、Slack Token）。

</details>

<details>
<summary><strong>哪些 AI 助手支持 MCP？</strong></summary>

截至 2026 年，支持 MCP 的助手包括：
- **Cursor** — 通过 `.cursor/mcp.json` 全面支持
- **Claude Code** — 通过 CLI（`claude mcp add`）全面支持
- **Kimi Code** — 通过 `AGENTS.md` 或 `config.toml` 全面支持
- **Windsurf**、**Cline**、**Continue** — 支持正在扩展中

</details>

<details>
<summary><strong>MCP 服务器安全吗？</strong></summary>

MCP 服务器运行在你本机上，只拥有你授予的权限。添加之前请先了解服务器的功能。在生产环境中使用时，建议限制文件路径并尽可能使用只读数据库连接。

</details>

<details>
<summary><strong>可以自己开发 MCP 服务器吗？</strong></summary>

当然可以。MCP SDK 提供了 [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) 和 [Python](https://github.com/modelcontextprotocol/python-sdk) 两种版本。详见[官方文档](https://modelcontextprotocol.io)。

</details>

<details>
<summary><strong>服务器不工作怎么排查？</strong></summary>

1. 确保已安装 Node.js 18+（或所需的运行时）
2. 尝试在终端手动运行该命令，查看错误信息
3. 检查是否已设置所需的环境变量或 API 密钥
4. 修改 MCP 配置后重启 AI 助手

</details>

---

## 相关项目

| 项目 | 说明 |
|------|------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20 个开箱即用的 AI 编程规则 |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — 为你的项目 AI 友好度打分 |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — AI 帮你写 commit 信息 |

## 参与贡献

我们欢迎贡献！详见 [CONTRIBUTING.md](CONTRIBUTING.md) 了解如何添加新的 MCP 服务器。

---

## 许可证

[MIT](LICENSE) — 随意使用。

---

<div align="center">

**由 MCP 社区用 ❤️ 打造**

[⬆ 回到顶部](#-awesome-mcp-servers--中文版)
