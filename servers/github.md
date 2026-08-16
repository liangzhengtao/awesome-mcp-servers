# GitHub MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The GitHub MCP server connects your AI assistant directly to the GitHub API. It can read repositories, browse issues and pull requests, search code, create branches, and manage your entire GitHub workflow — all through natural language. No more context-switching between your editor and the browser.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "ghp_your_token_here"
      }
    }
  }
}
```

### Claude Code

```bash
claude mcp add github --env GITHUB_PERSONAL_ACCESS_TOKEN=ghp_your_token_here -- npx -y @modelcontextprotocol/server-github
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- github: npx -y @modelcontextprotocol/server-github
```

Set `GITHUB_PERSONAL_ACCESS_TOKEN` as an environment variable or in `config.toml`.

## What You Can Do

- List and search repositories, issues, and pull requests
- Read file contents from any branch
- Create issues and pull requests with natural language
- Search code across repositories
- Manage branches and review PR diffs

## Requirements

- Node.js 18+
- A [GitHub Personal Access Token](https://github.com/settings/tokens) with appropriate scopes (`repo`, `read:org`, etc.)

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/github)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-github)
- [Documentation](https://modelcontextprotocol.io/docs/tools/github)
