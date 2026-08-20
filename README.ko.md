[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🚀 Awesome MCP Servers

**Cursor, Claude Code, Kimi Code를 위한 MCP 생태계. 하나의 설정 파일. 진정한 슈퍼파워.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servers)

<br/>

[MCP란?](#what-is-mcp) • [서버](#servers) • [빠른 시작](#quick-start) • [카테고리](#categories) • [FAQ](#faq) • [기여](CONTRIBUTING.md)

</div>

---

## MCP란?

**모델 컨텍스트 프로토콜(MCP)**은 AI 코딩 어시스턴트가 외부 도구, 데이터베이스, 서비스에 연결할 수 있게 해주는 개방형 표준입니다. AI가 고립된 상태로 작동하는 대신, MCP는 슈퍼파워를 부여합니다 — 데이터베이스를 쿼리하고, 레포를 관리하고, 웹을 검색하는 등 다양한 작업이 가능해집니다.

---

## Before / After

<table>
<tr>
<td width="50%" valign="top">

### ❌ MCP 없이

```
당신: "우리 Postgres에서 사용자 수를 확인해줘"
AI:  "데이터베이스에 접근할 수 없습니다."

당신: "GitHub의 최신 이슈를 봐줘"
AI:  "GitHub에 접근할 수 없습니다."

당신: "React 문서에서 hooks에 대해 뭐라고 하나요?"
AI:  "제 학습 데이터는 오래되었을 수 있습니다."
```

</td>
<td width="50%" valign="top">

### ✅ MCP 사용 시

```
당신: "우리 Postgres에서 사용자 수를 확인해줘"
AI:  → DB 쿼리 → "14,832명의 사용자가 있습니다."

당신: "GitHub의 최신 이슈를 봐줘"
AI:  → 이슈 읽기 → "열린 버그 3개, 기능 요청 2개."

당신: "React 문서에서 hooks에 대해 뭐라고 하나요?"
AI:  → 최신 문서 가져오기 → "최신 API입니다..."
```

</td>
</tr>
</table>

**MCP는 AI를 스마트 자동 완성에서 풀스택 엔지니어링 팀메이트로 변환합니다.**

---

## 서버

| # | 서버 | 카테고리 | 설명 | 패키지 |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 파일 | 로컬 파일 읽기, 쓰기, 관리 | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 개발 | 레포, 이슈, PR, 코드 검색 | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ 데이터베이스 | PostgreSQL 데이터베이스 쿼리 및 탐색 | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ 데이터베이스 | 캐시, pub/sub, 키-값 연산 | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 웹 | Brave 또는 Google로 웹 검색 | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 지식 | 영구 메모리 및 지식 그래프 | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 웹 | 브라우저 자동화 및 웹 스크래핑 | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 커뮤니케이션 | 메시지 전송 및 채널 관리 | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 문서 | 최신 라이브러리 문서 | `@upstash/context7-mcp` |

---

## 카테고리

| 카테고리 | 서버 | 설명 |
|----------|---------|-------------|
| [🔧 개발](by-category/development.md) | GitHub | 코드, 레포 |
| [🗄️ 데이터베이스](by-category/databases.md) | PostgreSQL, Redis | 쿼리, 저장, 캐시 |
| [💬 커뮤니케이션](by-category/communication.md) | Slack | 메시징 |
| 📁 파일 | Filesystem | 로컬 파일 연산 |
| 🌐 웹 | Web Search, Puppeteer | 검색, 브라우저 자동화 |
| 🧠 지식 | Memory, Context7 | 영구 컨텍스트, 최신 문서 |

---

## 빠른 시작

30초 이내에 AI 코딩 어시스턴트에 MCP 서버를 추가하세요.

### Cursor

1. 프로젝트 루트에 `.cursor/mcp.json`을 생성하거나 편집하세요:

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

2. Cursor를 재시작하세요. 하단 상태 표시줄에 MCP 서버 아이콘이 나타납니다.

### Claude Code

```bash
# Add a server with one command
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# Verify it's running
claude mcp list
```

### Kimi Code

Kimi Code 설정 디렉토리의 `config.toml`을 통해 설정하세요:

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## 여러 서버 동시 사용

필요한 만큼 서버를 쌓을 수 있습니다:

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
<summary><strong>MCP란 무엇인가요?</strong></summary>

모델 컨텍스트 프로토콜(MCP)은 Anthropic이 만든 개방형 표준으로, AI 어시스턴트가 외부 도구 및 데이터 소스에 연결하는 방법을 정의합니다. AI를 위한 유니버셜 어댑터라고 생각하세요 — 하나의 프로토콜, 어떤 도구든.

</details>

<details>
<summary><strong>MCP는 무료인가요?</strong></summary>

네. MCP 자체는 개방형 프로토콜(MIT 라이선스)입니다. 개별 MCP 서버는 로컬에서 무료로 실행할 수 있습니다. 일부는 타사 서비스(GitHub 토큰, Slack 토큰 등)에 대한 API 키가 필요할 수 있습니다.

</details>

<details>
<summary><strong>어떤 AI 어시스턴트가 MCP를 지원하나요?</strong></summary>

2026년 기준, MCP를 지원하는 도구:
- **Cursor** — `.cursor/mcp.json`을 통한 완전 지원
- **Claude Code** — CLI(`claude mcp add`)를 통한 완전 지원
- **Kimi Code** — `AGENTS.md` 또는 `config.toml`을 통한 완전 지원
- **Windsurf**, **Cline**, **Continue** — 점진적 지원

</details>

<details>
<summary><strong>MCP 서버는 안전한가요?</strong></summary>

MCP 서버는 로컬 머신에서 실행됩니다. 부여한 권한만 가지고 있습니다. 추가하기 전에 서버가 무엇을 하는지 항상 검토하세요. 프로덕션 사용 시에는 파일 경로를 제한하고 가능한 경우 읽기 전용 데이터베이스 연결을 사용하세요.

</details>

<details>
<summary><strong>직접 MCP 서버를 만들 수 있나요?</strong></summary>

물론입니다. MCP SDK는 [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk)와 [Python](https://github.com/modelcontextprotocol/python-sdk)에서 사용할 수 있습니다. 시작하려면 [공식 문서](https://modelcontextprotocol.io)를 참조하세요.

</details>

<details>
<summary><strong>작동하지 않는 서버를 어떻게 해결하나요?</strong></summary>

1. Node.js 18+(또는 필요한 런타임)이 설치되어 있는지 확인하세요
2. 터미널에서 명령어를 수동으로 실행하여 오류를 확인하세요
3. 필요한 환경 변수/API 키가 설정되어 있는지 확인하세요
4. MCP 설정을 변경한 후 AI 어시스턴트를 재시작하세요

</details>

---

## 관련 프로젝트

| 프로젝트 | 설명 |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20개 프로덕션 AI 코딩 규칙 |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — 프로젝트의 AI 준비도 점수 |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — AI가 커밋 메시지를 작성 |

## 기여

기여를 환영합니다! 새 MCP 서버를 추가하는 방법은 [CONTRIBUTING.md](CONTRIBUTING.md)를 참조하세요.

---

## 라이선스

[MIT](LICENSE) — 원하는 대로 사용하세요.

---

<div align="center">

**MCP 커뮤니티가 ❤️으로 만들었습니다**

[⬆ 맨 위로](#-awesome-mcp-servers)

</div>

---
