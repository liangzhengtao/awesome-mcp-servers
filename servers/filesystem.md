# Filesystem MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The Filesystem MCP server gives your AI assistant secure, sandboxed access to your local file system. It can read files, write files, search directories, and manage your project structure — all within paths you explicitly allow. Think of it as giving your AI a pair of hands to work with your codebase directly.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/your/project"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add filesystem -- npx -y @modelcontextprotocol/server-filesystem /path/to/your/project
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- filesystem: npx -y @modelcontextprotocol/server-filesystem /path/to/your/project
```

## What You Can Do

- Read any file in your project without copy-pasting
- Write and edit files programmatically
- Search for files by name pattern or content
- Create, move, and delete files and directories
- Get directory listings and project structure overviews

## Requirements

- Node.js 18+
- No API keys required — runs entirely locally

## Security Notes

- Only directories you explicitly specify are accessible
- The server respects your OS file permissions
- Use absolute paths to scope access precisely

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-filesystem)
- [Documentation](https://modelcontextprotocol.io/docs/tools/filesystem)
