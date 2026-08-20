[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🚀 Awesome MCP Servers

**L'écosystème MCP pour Cursor, Claude Code et Kimi Code. Un seul fichier de config. De vrais superpouvoirs.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#serveurs)

<br/>

[Qu'est-ce que MCP ?](#quest-ce-que-mcp) • [Serveurs](#serveurs) • [Démarrage rapide](#démarrage-rapide) • [Catégories](#catégories) • [FAQ](#faq) • [Contribuer](CONTRIBUTING.md)

</div>

---

## Qu'est-ce que MCP ?

Le **Model Context Protocol (MCP)** est un standard ouvert qui permet aux assistants IA de code de se connecter à des outils, bases de données et services externes. Au lieu que votre IA travaille de manière isolée, MCP lui confère des superpouvoirs — elle peut interroger votre base de données, gérer vos dépôts, naviguer sur le web, et bien plus encore.

---

## Avant / Après

<table>
<tr>
<td width="50%" valign="top">

### ❌ Sans MCP

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

### ✅ Avec MCP

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

**MCP transforme votre IA d'un simple outil d'auto-complétion en un coéquipier d'ingénierie full-stack.**

---

## Serveurs

| # | Serveur | Catégorie | Description | Paquet |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 Fichiers | Lire, écrire et gérer les fichiers locaux | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 Développement | Dépôts, issues, PR et recherche de code | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ Bases de données | Interroger et explorer les bases PostgreSQL | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ Bases de données | Cache, pub/sub et opérations clé-valeur | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 Web | Rechercher sur le web avec Brave ou Google | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 Connaissance | Mémoire persistante et graphe de connaissances | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 Web | Automatisation de navigateur et web scraping | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 Communication | Envoyer des messages et gérer les canaux | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 Documentation | Documentation à jour des bibliothèques | `@upstash/context7-mcp` |

---

## Catégories

| Catégorie | Serveurs | Description |
|----------|---------|-------------|
| [🔧 Développement](by-category/development.md) | GitHub | Code, dépôts |
| [🗄️ Bases de données](by-category/databases.md) | PostgreSQL, Redis | Requêtes, stockage, cache |
| [💬 Communication](by-category/communication.md) | Slack | Messagerie |
| 📁 Fichiers | Filesystem | Opérations sur fichiers locaux |
| 🌐 Web | Web Search, Puppeteer | Recherche, automatisation de navigateur |
| 🧠 Connaissance | Memory, Context7 | Contexte persistant, documentation en direct |

---

## Démarrage rapide

Ajoutez un serveur MCP à votre assistant IA de code en moins de 30 secondes.

### Cursor

1. Créez ou modifiez `.cursor/mcp.json` à la racine de votre projet :

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

2. Redémarrez Cursor. L'icône du serveur MCP apparaît dans la barre d'état.

### Claude Code

```bash
# Ajouter un serveur en une commande
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# Vérifier qu'il fonctionne
claude mcp list
```

### Kimi Code

Configurez via `config.toml` dans le répertoire de configuration de Kimi Code :

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## Plusieurs serveurs simultanément

Vous pouvez empiler autant de serveurs que nécessaire :

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
<summary><strong>Qu'est-ce que MCP ?</strong></summary>

Le Model Context Protocol (MCP) est un standard ouvert créé par Anthropic qui définit comment les assistants IA se connectent aux outils et sources de données externes. Pensez-y comme un adaptateur universel pour l'IA — un protocole, n'importe quel outil.

</details>

<details>
<summary><strong>MCP est-il gratuit ?</strong></summary>

Oui. MCP lui-même est un protocole ouvert (licence MIT). Les serveurs MCP individuels s'exécutent gratuitement en local. Certains peuvent nécessiter des clés API pour des services tiers (ex. : token GitHub, token Slack).

</details>

<details>
<summary><strong>Quels assistants IA supportent MCP ?</strong></summary>

En 2026, MCP est supporté par :
- **Cursor** — Support complet via `.cursor/mcp.json`
- **Claude Code** — Support complet via CLI (`claude mcp add`)
- **Kimi Code** — Support complet via `AGENTS.md` ou `config.toml`
- **Windsurf**, **Cline**, **Continue** — Support en expansion

</details>

<details>
<summary><strong>Les serveurs MCP sont-ils sûrs ?</strong></summary>

Les serveurs MCP s'exécutent localement sur votre machine. Ils ne disposent que des permissions que vous leur accordez. Examinez toujours ce que fait un serveur avant de l'ajouter. Pour un usage en production, restreignez les chemins de fichiers et utilisez des connexions en lecture seule à la base de données quand c'est possible.

</details>

<details>
<summary><strong>Puis-je construire mon propre serveur MCP ?</strong></summary>

Absolument. Le SDK MCP est disponible pour [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) et [Python](https://github.com/modelcontextprotocol/python-sdk). Consultez la [documentation officielle](https://modelcontextprotocol.io) pour commencer.

</details>

<details>
<summary><strong>Comment dépanner un serveur qui ne fonctionne pas ?</strong></summary>

1. Assurez-vous que Node.js 18+ (ou le runtime requis) est installé
2. Essayez d'exécuter la commande manuellement dans votre terminal pour voir les erreurs
3. Vérifiez que les variables d'environnement / clés API requises sont définies
4. Redémarrez votre assistant IA après avoir modifié la configuration MCP

</details>

---

## Voir aussi

| Projet | Description |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20 règles de code IA prêtes pour la production |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — Évaluez la préparation IA de votre projet |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — L'IA rédige vos messages de commit |

## Contribuer

Nous adorons les contributions ! Voir [CONTRIBUTING.md](CONTRIBUTING.md) pour savoir comment ajouter un nouveau serveur MCP.

---

## Licence

[MIT](LICENSE) — Utilisez-le comme vous le souhaitez.

---

<div align="center">

**Construit avec ❤️ par la communauté MCP**

[⬆ Retour en haut](#-awesome-mcp-servers)

</div>

---
