# 💬 Communication

MCP servers for team communication and collaboration.

## Servers

| Server | Description | Package | Status |
|--------|-------------|---------|--------|
| [Slack](../servers/slack.md) | Send messages and manage channels | `@modelcontextprotocol/server-slack` | Stable |

## Typical Workflows

### Stand-up Reporting

1. **GitHub** — List issues completed yesterday
2. **GitHub** — List issues planned for today
3. **Slack** — Post a formatted stand-up summary

### Incident Response

1. **GitHub** — Find the problematic commit
2. **Slack** — Notify the team in the incident channel

### Team Notifications

1. **GitHub** — PR merged or issue closed
2. **Slack** — Notify relevant channels

## Setup Tips

- Create a dedicated Slack bot app for MCP (don't reuse personal tokens)
- Scope Slack bot permissions to only the channels you need

## See Also

- [Development](development.md) — For code management
- [Databases](databases.md) — For data layer servers
