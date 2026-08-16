# Puppeteer MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The Puppeteer MCP server gives your AI assistant a full browser to work with. It can navigate websites, take screenshots, fill forms, click buttons, and scrape content — all through headless Chrome. Your AI can test web apps, extract data, and automate any browser-based workflow.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "puppeteer": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-puppeteer"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add puppeteer -- npx -y @modelcontextprotocol/server-puppeteer
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- puppeteer: npx -y @modelcontextprotocol/server-puppeteer
```

## What You Can Do

- Navigate to URLs and extract page content
- Take screenshots of full pages or specific elements
- Fill out forms and submit them
- Click buttons and interact with UI elements
- Execute JavaScript in the browser context
- Scrape structured data from web pages

## Requirements

- Node.js 18+
- ~300MB disk space (Chromium is bundled)
- No API keys required

## Performance Notes

- Headless mode is used by default (no visible browser window)
- Screenshots are returned as base64-encoded images
- For heavy scraping, consider adding delays between requests

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/puppeteer)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-puppeteer)
- [Documentation](https://modelcontextprotocol.io/docs/tools/puppeteer)
