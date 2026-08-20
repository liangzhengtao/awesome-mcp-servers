[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🚀 Awesome MCP Servers

**Экосистема MCP для Cursor, Claude Code и Kimi Code. Один файл настройки. Настоящие суперспособности.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servers)

<br/>

[Что такое MCP?](#what-is-mcp) • [Серверы](#servers) • [Быстрый старт](#quick-start) • [Категории](#categories) • [FAQ](#faq) • [Участие](CONTRIBUTING.md)

</div>

---

## Что такое MCP?

**Model Context Protocol (MCP)** — это открытый стандарт, позволяющий ИИ-ассистентам для кодирования подключаться к внешним инструментам, базам данных и сервисам. Вместо того чтобы ваш ИИ работал в изоляции, MCP даёт ему суперспособности — он может запрашивать вашу базу данных, управлять репозиториями, просматривать веб и многое другое.

---

## До / После

<table>
<tr>
<td width="50%" valign="top">

### ❌ Без MCP

```
Вы: "Проверь наш Postgres на количество пользователей"
ИИ: "Я не могу получить доступ к вашей базе данных."

Вы: "Посмотри последние issues на GitHub"
ИИ: "У меня нет доступа к GitHub."

Вы: "Что говорит документация React о хуках?"
ИИ: "Мои обучающие данные могут быть устаревшими."
```

</td>
<td width="50%" valign="top">

### ✅ С MCP

```
Вы: "Проверь наш Postgres на количество пользователей"
ИИ: → Запрашивает БД → "У вас 14 832 пользователя."

Вы: "Посмотри последние issues на GitHub"
ИИ: → Читает issues → "3 открытых бага, 2 запроса фичи."

Вы: "Что говорит документация React о хуках?"
ИИ: → Получает актуальные доки → "Вот последний API..."
```

</td>
</tr>
</table>

**MCP превращает вашего ИИ из умного автодополнения в полноценного инженерного тиммейта.**

---

## Серверы

| # | Сервер | Категория | Описание | Пакет |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 Файлы | Чтение, запись и управление локальными файлами | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 Разработка | Репозитории, issues, PR и поиск по коду | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ Базы данных | Запрос и исследование PostgreSQL баз данных | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ Базы данных | Кэш, pub/sub, операции ключ-значение | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 Веб | Поиск в интернете через Brave или Google | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 Знания | Постоянная память и граф знаний | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 Веб | Автоматизация браузера и веб-скрейпинг | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 Коммуникация | Отправка сообщений и управление каналами | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 Документация | Актуальная документация библиотек | `@upstash/context7-mcp` |

---

## Категории

| Категория | Серверы | Описание |
|----------|---------|-------------|
| [🔧 Разработка](by-category/development.md) | GitHub | Код, репозитории |
| [🗄️ Базы данных](by-category/databases.md) | PostgreSQL, Redis | Запросы, хранение, кэш |
| [💬 Коммуникация](by-category/communication.md) | Slack | Обмен сообщениями |
| 📁 Файлы | Filesystem | Работа с локальными файлами |
| 🌐 Веб | Web Search, Puppeteer | Поиск, автоматизация браузера |
| 🧠 Знания | Memory, Context7 | Постоянный контекст, актуальные доки |

---

## Быстрый старт

Добавьте MCP-сервер в ваш ИИ-ассистент для кодирования менее чем за 30 секунд.

### Cursor

1. Создайте или отредактируйте `.cursor/mcp.json` в корне проекта:

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

2. Перезапустите Cursor. Иконка MCP-сервера появится в нижней строке состояния.

### Claude Code

```bash
# Add a server with one command
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# Verify it's running
claude mcp list
```

### Kimi Code

Настройте через `config.toml` в директории конфигурации Kimi Code:

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## Несколько серверов одновременно

Вы можете подключить сколько угодно серверов:

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
<summary><strong>Что такое MCP?</strong></summary>

Model Context Protocol (MCP) — это открытый стандарт, созданный Anthropic, определяющий, как ИИ-ассистенты подключаются к внешним инструментам и источникам данных. Представьте его как универсальный адаптер для ИИ — один протокол, любой инструмент.

</details>

<details>
<summary><strong>MCP бесплатен?</strong></summary>

Да. Сам MCP — открытый протокол (лицензия MIT). Отдельные MCP-серверы бесплатны для запуска локально. Некоторые могут требовать API-ключи для сторонних сервисов (например, токен GitHub, токен Slack).

</details>

<details>
<summary><strong>Какие ИИ-ассистенты поддерживают MCP?</strong></summary>

По состоянию на 2026 год MCP поддерживается:
- **Cursor** — Полная поддержка через `.cursor/mcp.json`
- **Claude Code** — Полная поддержка через CLI (`claude mcp add`)
- **Kimi Code** — Полная поддержка через `AGENTS.md` или `config.toml`
- **Windsurf**, **Cline**, **Continue** — Растущая поддержка

</details>

<details>
<summary><strong>MCP-серверы безопасны?</strong></summary>

MCP-серверы работают локально на вашей машине. Они имеют только те разрешения, которые вы им даёте. Всегда проверяйте, что делает сервер, перед его добавлением. Для продакшн-использования ограничивайте пути к файлам и используйте подключения к БД только для чтения, где это возможно.

</details>

<details>
<summary><strong>Могу ли я создать свой MCP-сервер?</strong></summary>

Конечно. MCP SDK доступен для [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) и [Python](https://github.com/modelcontextprotocol/python-sdk). Смотрите [официальную документацию](https://modelcontextprotocol.io) для начала работы.

</details>

<details>
<summary><strong>Как устранить неполадки с неработающим сервером?</strong></summary>

1. Убедитесь, что установлен Node.js 18+ (или необходимый рантайм)
2. Попробуйте запустить команду вручную в терминале, чтобы увидеть ошибки
3. Проверьте, что необходимые переменные окружения / API-ключи установлены
4. Перезапустите ИИ-ассистент после изменения конфигурации MCP

</details>

---

## Также посмотрите

| Проект | Описание |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20 продакшн-правил ИИ-кодирования |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — Оцените готовность вашего проекта к ИИ |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — ИИ пишет ваши коммит-сообщения |

## Участие

Мы любим вклады! Смотрите [CONTRIBUTING.md](CONTRIBUTING.md), чтобы узнать, как добавить новый MCP-сервер.

---

## Лицензия

[MIT](LICENSE) — Используйте как угодно.

---

<div align="center">

**Создано с ❤️ сообществом MCP**

[⬆ Наверх](#-awesome-mcp-servers)

</div>

---
