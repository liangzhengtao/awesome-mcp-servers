# Slack MCP Server

> Last updated: 2026 | Status: Stable | Maintained by: Anthropic (Model Context Protocol team)

## What It Does

The Slack MCP server connects your AI assistant to your Slack workspace. It can send messages, read channel history, manage threads, and search conversations — all through natural language. Your AI becomes a bridge between your code and your team communication.

## Quick Setup

### Cursor

```json
// .cursor/mcp.json
{
  "mcpServers": {
    "slack": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-slack"],
      "env": {
        "SLACK_BOT_TOKEN": "xoxb-your-bot-token",
        "SLACK_TEAM_ID": "T01234567"
      }
    }
  }
}
```

### Claude Code

```bash
claude mcp add slack --env SLACK_BOT_TOKEN=xoxb-your-bot-token --env SLACK_TEAM_ID=T01234567 -- npx -y @modelcontextprotocol/server-slack
```

### Kimi Code

```markdown
<!-- AGENTS.md -->
## MCP Servers
- slack: npx -y @modelcontextprotocol/server-slack
```

Set `SLACK_BOT_TOKEN` and `SLACK_TEAM_ID` as environment variables.

## What You Can Do

- Send messages to channels and users
- Read channel history and thread replies
- Search messages across your workspace
- Create and manage channels
- React to messages and manage threads

## Requirements

- Node.js 18+
- A [Slack App](https://api.slack.com/apps) with Bot Token Scopes: `channels:history`, `channels:read`, `chat:write`, `groups:history`, `groups:read`, `search:read`
- Install the app to your workspace and copy the Bot User OAuth Token

## Links

- [GitHub](https://github.com/modelcontextprotocol/servers/tree/main/src/slack)
- [npm](https://www.npmjs.com/package/@modelcontextprotocol/server-slack)
- [Documentation](https://modelcontextprotocol.io/docs/tools/slack)
- [Slack API Apps](https://api.slack.com/apps)
