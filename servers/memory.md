# Memory MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The Memory MCP server gives your AI assistant persistent memory across conversations using a local knowledge graph. It stores entities, relationships, and observations so your AI remembers context between sessions — your project architecture, team conventions, past decisions, and technical preferences.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "memory": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-memory"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add memory -- npx -y @modelcontextprotocol/server-memory
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- memory: npx -y @modelcontextprotocol/server-memory
```

## What You Can Do

- Store project context that persists across sessions
- Build a knowledge graph of entities and relationships
- Remember team conventions, coding standards, and decisions
- Track project history and architectural evolution
- Share context across different AI assistants

## How It Works

The Memory server uses a local knowledge graph stored as JSON:

- **Entities** — things like "Project X", "Team Backend", "Database: PostgreSQL"
- **Relations** — connections like "Project X → uses → PostgreSQL"
- **Observations** — facts like "Project X uses TypeScript strict mode"

## Requirements

- Node.js 18+
- No API keys required — data is stored locally
- ~1MB disk space for typical usage

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/memory)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-memory)
- [Documentation](https://modelcontextprotocol.io/docs/tools/memory)
