# Context7 MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Upstash

## What It Does

Context7 fetches up-to-date, version-specific library documentation and feeds it directly to your AI assistant. No more hallucinated APIs or outdated examples — your AI gets the real docs for the exact library version you're using. Think of it as giving your AI a live connection to every library's documentation.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "context7": {
      "command": "npx",
      "args": ["-y", "@upstash/context7-mcp"]
    }
  }
}
```

### Claude Code

```bash
claude mcp add context7 -- npx -y @upstash/context7-mcp
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- context7: npx -y @upstash/context7-mcp
```

## What You Can Do

- Fetch the latest docs for any library before writing code
- Get version-specific API references (e.g., Next.js 15 vs 14)
- Look up correct function signatures and usage examples
- Avoid hallucinated APIs that don't actually exist
- Access documentation for 1000+ popular libraries

## How It Works

1. Your AI identifies which library it needs docs for
2. Context7 fetches the relevant, up-to-date documentation
3. The docs are injected into the AI's context
4. The AI writes code based on real, current documentation

## Requirements

- Node.js 18+
- No API keys required — uses the free Context7 service

## Links

- [GitHub](https://github.com/upstash/context7)
- [npm](https://www.npmjs.com/package/@upstash/context7-mcp)
- [Context7 Website](https://context7.com)
