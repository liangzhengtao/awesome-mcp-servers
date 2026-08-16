# Web Search MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The Web Search MCP server connects your AI assistant to the internet, allowing it to search the web using Brave Search or Google. Your AI can look up documentation, find solutions to errors, research APIs, and stay current with the latest information — no more "my training data may be outdated" disclaimers.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "web-search": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-brave-search"],
      "env": {
        "BRAVE_API_KEY": "your_brave_api_key_here"
      }
    }
  }
}
```

### Claude Code

```bash
claude mcp add web-search --env BRAVE_API_KEY=your_brave_api_key_here -- npx -y @modelcontextprotocol/server-brave-search
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- web-search: npx -y @modelcontextprotocol/server-brave-search
```

Set `BRAVE_API_KEY` as an environment variable.

## What You Can Do

- Search the web for any topic in real-time
- Look up library documentation and API references
- Find solutions to error messages and bugs
- Research best practices and design patterns
- Get current news and updates on technologies

## Requirements

- Node.js 18+
- A [Brave Search API key](https://brave.com/search/api/) (free tier available with 2,000 queries/month)

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/brave-search)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-brave-search)
- [Documentation](https://modelcontextprotocol.io/docs/tools/brave-search)
- [Brave API Keys](https://brave.com/search/api/)
