[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🚀 Awesome MCP Servers

**El ecosistema MCP para Cursor, Claude Code y Kimi Code. Un solo archivo de config. Superpoderes de verdad.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servidores)

<br/>

[¿Qué es MCP?](#qué-es-mcp) • [Servidores](#servidores) • [Inicio rápido](#inicio-rápido) • [Categorías](#categorías) • [FAQ](#faq) • [Contribuir](CONTRIBUTING.md)

</div>

---

## ¿Qué es MCP?

El **Model Context Protocol (MCP)** es un estándar abierto que permite a los asistentes IA de código conectarse a herramientas, bases de datos y servicios externos. En lugar de que tu IA trabaje de forma aislada, MCP le otorga superpoderes — puede consultar tu base de datos, gestionar tus repos, navegar por la web y mucho más.

---

## Antes / Después

<table>
<tr>
<td width="50%" valign="top">

### ❌ Sin MCP

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

### ✅ Con MCP

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

**MCP transforma tu IA de un simple autocompletado en un compañero de ingeniería full-stack.**

---

## Servidores

| # | Servidor | Categoría | Descripción | Paquete |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 Archivos | Leer, escribir y gestionar archivos locales | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 Desarrollo | Repos, issues, PR y búsqueda de código | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ Bases de datos | Consultar y explorar bases de datos PostgreSQL | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ Bases de datos | Caché, pub/sub y operaciones clave-valor | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 Web | Buscar en la web con Brave o Google | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 Conocimiento | Memoria persistente y grafo de conocimiento | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 Web | Automatización de navegador y web scraping | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 Comunicación | Enviar mensajes y gestionar canales | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 Documentación | Documentación actualizada de bibliotecas | `@upstash/context7-mcp` |

---

## Categorías

| Categoría | Servidores | Descripción |
|----------|---------|-------------|
| [🔧 Desarrollo](by-category/development.md) | GitHub | Código, repos |
| [🗄️ Bases de datos](by-category/databases.md) | PostgreSQL, Redis | Consultas, almacenamiento, caché |
| [💬 Comunicación](by-category/communication.md) | Slack | Mensajería |
| 📁 Archivos | Filesystem | Operaciones con archivos locales |
| 🌐 Web | Web Search, Puppeteer | Búsqueda, automatización de navegador |
| 🧠 Conocimiento | Memory, Context7 | Contexto persistente, documentación en vivo |

---

## Inicio rápido

Añade un servidor MCP a tu asistente IA de código en menos de 30 segundos.

### Cursor

1. Crea o edita `.cursor/mcp.json` en la raíz de tu proyecto:

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

2. Reinicia Cursor. El icono del servidor MCP aparece en la barra de estado inferior.

### Claude Code

```bash
# Añadir un servidor con un solo comando
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# Verificar que funciona
claude mcp list
```

### Kimi Code

Configura mediante `config.toml` en el directorio de configuración de Kimi Code:

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## Múltiples servidores a la vez

Puedes apilar tantos servidores como necesites:

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
<summary><strong>¿Qué es MCP?</strong></summary>

El Model Context Protocol (MCP) es un estándar abierto creado por Anthropic que define cómo los asistentes IA se conectan a herramientas y fuentes de datos externas. Piensa en él como un adaptador universal para IA — un protocolo, cualquier herramienta.

</details>

<details>
<summary><strong>¿Es gratuito MCP?</strong></summary>

Sí. MCP en sí es un protocolo abierto (licencia MIT). Los servidores MCP individuales se ejecutan gratis en local. Algunos pueden requerir claves API para servicios de terceros (ej.: token de GitHub, token de Slack).

</details>

<details>
<summary><strong>¿Qué asistentes IA soportan MCP?</strong></summary>

A partir de 2026, MCP está soportado por:
- **Cursor** — Soporte completo vía `.cursor/mcp.json`
- **Claude Code** — Soporte completo vía CLI (`claude mcp add`)
- **Kimi Code** — Soporte completo vía `AGENTS.md` o `config.toml`
- **Windsurf**, **Cline**, **Continue** — Soporte en expansión

</details>

<details>
<summary><strong>¿Son seguros los servidores MCP?</strong></summary>

Los servidores MCP se ejecutan localmente en tu máquina. Solo tienen los permisos que les otorgues. Siempre revisa qué hace un servidor antes de añadirlo. Para uso en producción, restringe las rutas de archivos y usa conexiones de solo lectura a la base de datos cuando sea posible.

</details>

<details>
<summary><strong>¿Puedo construir mi propio servidor MCP?</strong></summary>

Por supuesto. El SDK MCP está disponible para [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) y [Python](https://github.com/modelcontextprotocol/python-sdk). Consulta la [documentación oficial](https://modelcontextprotocol.io) para empezar.

</details>

<details>
<summary><strong>¿Cómo solucionar problemas con un servidor que no funciona?</strong></summary>

1. Asegúrate de tener Node.js 18+ (o el runtime requerido) instalado
2. Intenta ejecutar el comando manualmente en tu terminal para ver los errores
3. Verifica que las variables de entorno / claves API necesarias estén configuradas
4. Reinicia tu asistente IA después de cambiar la configuración de MCP

</details>

---

## Ver también

| Proyecto | Descripción |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20 reglas de código IA listas para producción |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — Evalúa la preparación IA de tu proyecto |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — La IA escribe tus mensajes de commit |

## Contribuir

¡Nos encantan las contribuciones! Consulta [CONTRIBUTING.md](CONTRIBUTING.md) para saber cómo añadir un nuevo servidor MCP.

---

## Licencia

[MIT](LICENSE) — Úsalo como quieras.

---

<div align="center">

**Construido con ❤️ por la comunidad MCP**

[⬆ Volver arriba](#-awesome-mcp-servers)

</div>

---
