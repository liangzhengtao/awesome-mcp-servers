# Redis MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The Redis MCP server gives your AI assistant direct access to Redis for caching, key-value operations, pub/sub messaging, and data structure manipulation. Whether you're debugging cache issues or building real-time features, your AI can interact with Redis as naturally as writing code.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "redis": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-redis", "redis://localhost:6379"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add redis -- npx -y @modelcontextprotocol/server-redis redis://localhost:6379
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- redis: npx -y @modelcontextprotocol/server-redis redis://localhost:6379
```

## What You Can Do

- Get, set, and delete keys with natural language
- Inspect data structures (hashes, lists, sets, sorted sets)
- Monitor pub/sub channels and messages
- Debug cache behavior and TTL issues
- Run Lua scripts and transactions

## Requirements

- Node.js 18+
- A running Redis instance (local or remote)
- Redis connection URL (supports `redis://` and `rediss://` for TLS)

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/redis)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-redis)
- [Documentation](https://modelcontextprotocol.io/docs/tools/redis)
