[English](README.md) | [中文](README.zh.md) | [日本語](README.ja.md) | [Français](README.fr.md) | [Español](README.es.md) | [العربية](README.ar.md) | [한국어](README.ko.md) | [Português](README.pt.md) | [Русский](README.ru.md) | [Deutsch](README.de.md)

<div align="center">

<img src=".banner.svg" width="100%" alt="banner">

</div>


<div align="center">

# 🚀 Awesome MCP Servers

**O ecossistema MCP para Cursor, Claude Code e Kimi Code. Um arquivo de configuração. Superpoderes reais.**

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Servers](https://img.shields.io/badge/Servers-9-blue)](#servers)

<br/>

[O que é MCP?](#what-is-mcp) • [Servidores](#servers) • [Início Rápido](#quick-start) • [Categorias](#categories) • [FAQ](#faq) • [Contribuindo](CONTRIBUTING.md)

</div>

---

## O que é MCP?

O **Model Context Protocol (MCP)** é um padrão aberto que permite que assistentes de código com IA se conectem a ferramentas, bancos de dados e serviços externos. Em vez da sua IA trabalhar isoladamente, o MCP lhe dá superpoderes — ela pode consultar seu banco de dados, gerenciar seus repositórios, navegar na web e muito mais.

---

## Antes / Depois

<table>
<tr>
<td width="50%" valign="top">

### ❌ Sem MCP

```
Você: "Verifique nosso Postgres para contagem de usuários"
AI:  "Não consigo acessar seu banco de dados."

Você: "Veja as últimas issues no GitHub"
AI:  "Não tenho acesso ao GitHub."

Você: "O que a documentação do React diz sobre hooks?"
AI:  "Meus dados de treinamento podem estar desatualizados."
```

</td>
<td width="50%" valign="top">

### ✅ Com MCP

```
Você: "Verifique nosso Postgres para contagem de usuários"
AI:  → Consulta seu BD → "Você tem 14.832 usuários."

Você: "Veja as últimas issues no GitHub"
AI:  → Lê as issues → "3 bugs abertos, 2 pedidos de funcionalidade."

Você: "O que a documentação do React diz sobre hooks?"
AI:  → Busca docs atualizados → "Aqui está a API mais recente..."
```

</td>
</tr>
</table>

**O MCP transforma sua IA de um autocomplete inteligente em um membro da equipe de engenharia full-stack.**

---

## Servidores

| # | Servidor | Categoria | Descrição | Pacote |
|---|--------|----------|-------------|---------|
| 1 | [Filesystem](servers/filesystem.md) | 📁 Arquivos | Ler, escrever e gerenciar arquivos locais | `@modelcontextprotocol/server-filesystem` |
| 2 | [GitHub](servers/github.md) | 🔧 Desenvolvimento | Repos, issues, PRs e busca de código | `@modelcontextprotocol/server-github` |
| 3 | [PostgreSQL](servers/postgres.md) | 🗄️ Bancos de Dados | Consultar e explorar bancos PostgreSQL | `@modelcontextprotocol/server-postgres` |
| 4 | [Redis](servers/redis.md) | 🗄️ Bancos de Dados | Cache, pub/sub e operações chave-valor | `@modelcontextprotocol/server-redis` |
| 5 | [Web Search](servers/web-search.md) | 🌐 Web | Pesquisar na web com Brave ou Google | `@modelcontextprotocol/server-brave-search` |
| 6 | [Memory](servers/memory.md) | 🧠 Conhecimento | Memória persistente e grafo de conhecimento | `@modelcontextprotocol/server-memory` |
| 7 | [Puppeteer](servers/puppeteer.md) | 🌐 Web | Automação de navegador e web scraping | `@modelcontextprotocol/server-puppeteer` |
| 8 | [Slack](servers/slack.md) | 💬 Comunicação | Enviar mensagens e gerenciar canais | `@modelcontextprotocol/server-slack` |
| 9 | [Context7](servers/context7.md) | 📚 Documentação | Documentação atualizada de bibliotecas | `@upstash/context7-mcp` |

---

## Categorias

| Categoria | Servidores | Descrição |
|----------|---------|-------------|
| [🔧 Desenvolvimento](by-category/development.md) | GitHub | Código, repos |
| [🗄️ Bancos de Dados](by-category/databases.md) | PostgreSQL, Redis | Consultar, armazenar, cache |
| [💬 Comunicação](by-category/communication.md) | Slack | Mensageria |
| 📁 Arquivos | Filesystem | Operações de arquivos locais |
| 🌐 Web | Web Search, Puppeteer | Pesquisa, automação de navegador |
| 🧠 Conhecimento | Memory, Context7 | Contexto persistente, docs atualizados |

---

## Início Rápido

Adicione um servidor MCP ao seu assistente de código com IA em menos de 30 segundos.

### Cursor

1. Crie ou edite `.cursor/mcp.json` na raiz do seu projeto:

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

2. Reinicie o Cursor. O ícone do servidor MCP aparece na barra de status inferior.

### Claude Code

```bash
# Add a server with one command
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project

# Verify it's running
claude mcp list
```

### Kimi Code

Configure via `config.toml` no diretório de configuração do Kimi Code:

```toml
[mcp_servers.filesystem]
command = "npx"
args = ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
```

---

## Múltiplos Servidores ao Mesmo Tempo

Você pode empilhar quantos servidores precisar:

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
<summary><strong>O que é MCP?</strong></summary>

O Model Context Protocol (MCP) é um padrão aberto criado pela Anthropic que define como assistentes de IA se conectam a ferramentas e fontes de dados externas. Pense nele como um adaptador universal para IA — um protocolo, qualquer ferramenta.

</details>

<details>
<summary><strong>MCP é gratuito?</strong></summary>

Sim. O próprio MCP é um protocolo aberto (licenciado sob MIT). Servidores MCP individuais são gratuitos para execução local. Alguns podem exigir chaves de API para serviços de terceiros (ex: token GitHub, token Slack).

</details>

<details>
<summary><strong>Quais assistentes de IA suportam MCP?</strong></summary>

Em 2026, o MCP é suportado por:
- **Cursor** — Suporte total via `.cursor/mcp.json`
- **Claude Code** — Suporte total via CLI (`claude mcp add`)
- **Kimi Code** — Suporte total via `AGENTS.md` ou `config.toml`
- **Windsurf**, **Cline**, **Continue** — Suporte crescente

</details>

<details>
<summary><strong>Servidores MCP são seguros?</strong></summary>

Servidores MCP rodam localmente na sua máquina. Eles só têm as permissões que você concede. Sempre revise o que um servidor faz antes de adicioná-lo. Para uso em produção, restrinja caminhos de arquivo e use conexões de banco de dados somente leitura quando possível.

</details>

<details>
<summary><strong>Posso criar meu próprio servidor MCP?</strong></summary>

Com certeza. O SDK do MCP está disponível para [TypeScript](https://github.com/modelcontextprotocol/typescript-sdk) e [Python](https://github.com/modelcontextprotocol/python-sdk). Veja a [documentação oficial](https://modelcontextprotocol.io) para começar.

</details>

<details>
<summary><strong>Como faço troubleshooting de um servidor que não funciona?</strong></summary>

1. Certifique-se de que o Node.js 18+ (ou o runtime necessário) está instalado
2. Tente executar o comando manualmente no terminal para ver erros
3. Verifique se as variáveis de ambiente / chaves API necessárias estão configuradas
4. Reinicie seu assistente de IA após alterar a config do MCP

</details>

---

## Veja Também

| Projeto | Descrição |
|---------|-------------|
| [**awesome-ai-rules**](https://github.com/liangzhengtao/awesome-ai-rules) | 20 regras de código IA para produção |
| [**vibe-check**](https://github.com/liangzhengtao/vibe-check) | `npx vibe-check` — Avalie a prontidão do seu projeto para IA |
| [**ai-commit**](https://github.com/liangzhengtao/ai-commit) | `npx ai-commit` — IA escreve suas mensagens de commit |

## Contribuindo

Adoramos contribuições! Veja [CONTRIBUTING.md](CONTRIBUTING.md) para saber como adicionar um novo servidor MCP.

---

## Licença

[MIT](LICENSE) — Use como quiser.

---

<div align="center">

**Feito com ❤️ pela comunidade MCP**

[⬆ Voltar ao topo](#-awesome-mcp-servers)

</div>

---
