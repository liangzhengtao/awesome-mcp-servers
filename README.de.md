[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🚀 Awesome MCP Servers

**Das MCP-Ökosystem für Cursor, Claude Code und Kimi Code. Eine Konfigurationsdatei. Echte Superkräfte.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servers)

<br/>

[Was ist MCP?](#what-is-mcp) • [Server](#servers) • [Schnellstart](#quick-start) • [Kategorien](#categories) • [FAQ](#faq) • [Mitwirken](CONTRIBUTING.md)

</div>

---

## Was ist MCP?

Das **Model Context Protocol (MCP)** ist ein offener Standard, der es KI-Coding-Assistenten ermöglicht, sich mit externen Tools, Datenbanken und Diensten zu verbinden. Anstatt dass Ihre KI isoliert arbeitet, gibt ihr MCP Superkräfte — sie kann Ihre Datenbank abfragen, Ihre Repos verwalten, das Web durchsuchen und vieles mehr.

---

## Vorher / Nachher

<table>
<tr>
<td width="50%" valign="top">

### ❌ Ohne MCP

```
Sie: "Prüfe unsere Postgres-Datenbank auf die Benutzerzahl"
KI:  "Ich kann nicht auf Ihre Datenbank zugreifen."

Sie: "Schau dir die neuesten Issues auf GitHub an"
KI:  "Ich habe keinen Zugriff auf GitHub."

Sie: "Was sagt die React-Dokumentation über Hooks?"
KI:  "Meine Trainingsdaten sind möglicherweise veraltet."
```

</td>
<td width="50%" valign="top">

### ✅ Mit MCP

```
Sie: "Prüfe unsere Postgres-Datenbank auf die Benutzerzahl"
KI:  → Fragt Ihre DB ab → "Sie haben 14.832 Benutzer."

Sie: "Schau dir die neuesten Issues auf GitHub an"
KI:  → Liest Issues → "3 offene Bugs, 2 Feature-Anfragen."

Sie: "Was sagt die React-Dokumentation über Hooks?"
KI:  → Holt aktuelle Docs → "Hier ist die neueste API..."
```

</td>
</tr>
</table>

**MCP verwandelt Ihre KI von einem intelligenten Autocomplete in einen Full-Stack-Engineering-Teammate.**

---

## Server

| # | Server | Kategorie | Beschreibung | Paket |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 Dateien | Lokale Dateien lesen, schreiben und verwalten | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 Entwicklung | Repos, Issues, PRs und Codesuche | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ Datenbanken | PostgreSQL-Datenbanken abfragen und erkunden | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ Datenbanken | Cache, Pub/Sub und Key-Value-Operationen | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 Web | Websuche mit Brave oder Google | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 Wissen | Persistenter Speicher und Wissensgraph | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 Web | Browser-Automatisierung und Web-Scraping | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 Kommunikation | Nachrichten senden und Kanäle verwalten | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 Dokumentation | Aktuelle Bibliotheks-Dokumentation | `@upstash/context7-mcp` |

---

## Kategorien

| Kategorie | Server | Beschreibung |
|----------|---------|-------------|
| [🔧 Entwicklung](by-category/development.md) | GitHub | Code, Repos |
| [🗄️ Datenbanken](by-category/databases.md) | PostgreSQL, Redis | Abfragen, Speichern, Cache |
| [💬 Kommunikation](by-category/communication.md) | Slack | Messaging |
| 📁 Dateien | Filesystem | Lokale Dateioperationen |
| 🌐 Web | Web Search, Puppeteer | Suche, Browser-Automatisierung |
| 🧠 Wissen | Memory, Context7 | Persistenter Kontext, aktuelle Docs |

---

## Schnellstart

Fügen Sie einen MCP-Server in weniger als 30 Sekunden zu Ihrem KI-Coding-Assistenten hinzu.

### Cursor

1. Erstellen oder bearbeiten Sie `.cursor/mcp.json` in Ihrem Projekt-Stammverzeichnis:

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

2. Starten Sie Cursor neu. Das MCP-Server-Symbol erscheint in der unteren Statusleiste.

### Claude Code

```bash
# Add a server with one command
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# Verify it's running
claude mcp list
```

### Kimi Code

Konfigurieren Sie über `config.toml` im Kimi Code-Konfigurationsverzeichnis:

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## Mehrere Server gleichzeitig

Sie können so viele Server stapeln, wie Sie benötigen:

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
<summary><strong>Was ist MCP?</strong></summary>

Das Model Context Protocol (MCP) ist ein offener Standard von Anthropic, der definiert, wie KI-Assistenten sich mit externen Tools und Datenquellen verbinden. Stellen Sie es sich als Universaladapter für KI vor — ein Protokoll, jedes Tool.

</details>

<details>
<summary><strong>Ist MCP kostenlos?</strong></summary>

Ja. MCP selbst ist ein offenes Protokoll (MIT-Lizenz). Einzelne MCP-Server sind kostenlos lokal ausführbar. Einige benötigen möglicherweise API-Schlüssel für Drittanbieter-Dienste (z.B. GitHub-Token, Slack-Token).

</details>

<details>
<summary><strong>Welche KI-Assistenten unterstützen MCP?</strong></summary>

Stand 2026 wird MCP unterstützt von:
- **Cursor** — Vollständige Unterstützung über `.cursor/mcp.json`
- **Claude Code** — Vollständige Unterstützung über CLI (`claude mcp add`)
- **Kimi Code** — Vollständige Unterstützung über `AGENTS.md` oder `config.toml`
- **Windsurf**, **Cline**, **Continue** — Wachsende Unterstützung

</details>

<details>
<summary><strong>Sind MCP-Server sicher?</strong></summary>

MCP-Server laufen lokal auf Ihrem Rechner. Sie haben nur die Berechtigungen, die Sie ihnen erteilen. Überprüfen Sie immer, was ein Server tut, bevor Sie ihn hinzufügen. Für den Produktionseinsatz schränken Sie Dateipfade ein und verwenden Sie nach Möglichkeit schreibgeschützte Datenbankverbindungen.

</details>

<details>
<summary><strong>Kann ich meinen eigenen MCP-Server bauen?</strong></summary>

Absolut. Das MCP-SDK ist verfügbar für [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) und [Python](https://github.com/modelcontextprotocol/python-sdk). In der [offiziellen Dokumentation](https://modelcontextprotocol.io) finden Sie alles zum Einstieg.

</details>

<details>
<summary><strong>Wie troubleshoote ich einen nicht funktionierenden Server?</strong></summary>

1. Stellen Sie sicher, dass Node.js 18+ (oder die benötigte Runtime) installiert ist
2. Versuchen Sie, den Befehl manuell im Terminal auszuführen, um Fehler zu sehen
3. Prüfen Sie, ob erforderliche Umgebungsvariablen / API-Schlüssel gesetzt sind
4. Starten Sie Ihren KI-Assistenten nach Änderungen der MCP-Konfiguration neu

</details>

---

## Siehe auch

| Projekt | Beschreibung |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20 produktionsreife KI-Coding-Regeln |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — Bewerten Sie die KI-Bereitschaft Ihres Projekts |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — KI schreibt Ihre Commit-Nachrichten |

## Mitwirken

Wir lieben Beiträge! Siehe [CONTRIBUTING.md](CONTRIBUTING.md), um einen neuen MCP-Server hinzuzufügen.

---

## Lizenz

[MIT](LICENSE) — Nutzen Sie es, wie Sie möchten.

---

<div align="center">

**Erstellt mit ❤️ von der MCP-Community**

[⬆ Zurück nach oben](#-awesome-mcp-servers)

</div>

---
