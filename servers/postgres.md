# PostgreSQL MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The PostgreSQL MCP server lets your AI assistant query, explore, and manage PostgreSQL databases directly. It can run SQL queries, inspect schemas, analyze table structures, and help you understand your data — all through conversation. No more copy-pasting query results.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "postgres": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-postgres", "postgresql://user:password@localhost:5432/mydb"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add postgres -- npx -y @modelcontextprotocol/server-postgres postgresql://user:password@localhost:5432/mydb
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- postgres: npx -y @modelcontextprotocol/server-postgres postgresql://user:password@localhost:5432/mydb
```

## What You Can Do

- Run SQL queries and get formatted results
- Explore database schemas and table structures
- Analyze data distributions and relationships
- Debug query performance issues
- Generate migration scripts based on schema changes

## Requirements

- Node.js 18+
- A running PostgreSQL instance (local or remote)
- Connection string with appropriate permissions

## Security Notes

- Use read-only connections for production databases
- Prefer a dedicated user with limited permissions
- Never commit connection strings with passwords to version control

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-postgres)
- [Documentation](https://modelcontextprotocol.io/docs/tools/postgres)
