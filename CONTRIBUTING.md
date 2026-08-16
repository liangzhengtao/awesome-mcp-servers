# Contributing to Awesome MCP Servers

Thanks for your interest in contributing! This project is a curated list of MCP servers, and we welcome additions that help the community.

## How to Add a New MCP Server

### 1. Check Eligibility

Your MCP server should meet these criteria:

- **Functional** — It works with at least one major AI assistant (Cursor, Claude Code, Kimi Code)
- **Documented** — It has a README with setup instructions
- **Maintained** — It has been updated within the last 6 months
- **Useful** — It solves a real problem for developers

### 2. Create the Server File

Create a new file in `servers/` named `<server-name>.md` using this template:

```markdown
# Server Name

> Last updated: YYYY | Status: Stable/Beta | Maintained by: Author or Org

## What It Does

[2-3 sentences describing what the server does and why it's useful.]

## Quick Setup

### Cursor

\```json
// .cursor/mcp.json
{
  "mcpServers": {
    "server-name": {
      "command": "npx",
      "args": ["-y", "@package/name"]
    }
  }
}
\```

### Claude Code

\```bash
claude mcp add server-name -- npx -y @package/name
\```

### Kimi Code

\```markdown
<!-- AGENTS.md -->
## MCP Servers
- server-name: npx -y @package/name
\```

## What You Can Do

- [Specific capability 1]
- [Specific capability 2]
- [Specific capability 3]

## Requirements

- [Runtime version, e.g., Node.js 18+]
- [Any API keys or services needed]

## Links

- [GitHub](https://github.com/...)
- [npm](https://www.npmjs.com/package/...)
- [Documentation](https://...)
```

### 3. Update the README

Add your server to the main table in `README.md`:

```markdown
| # | Server | Category | Description | Package |
|---|--------|----------|-------------|---------|
| ... | [Your Server](servers/your-server.md) | 📋 Category | Short description | `@package/name` |
```

### 4. Update Category Index (if applicable)

If your server fits an existing category in `by-category/`, add it to the table there.

If it introduces a new category:

1. Create `by-category/<category>.md` using the existing category files as a template
2. Add a row to the Categories table in `README.md`

### 5. Submit a Pull Request

1. Fork the repository
2. Create a branch: `git checkout -b add-server-name`
3. Commit your changes: `git commit -m "Add Server Name MCP server"`
4. Push to your fork: `git push origin add-server-name`
5. Open a Pull Request using the [PR template](.github/pull_request_template.md)

## Updating an Existing Server

If a server's information is outdated:

1. Update the relevant file in `servers/`
2. Bump the `Last updated` date
3. Submit a PR with a description of what changed

## Reporting Issues

Found a broken link, outdated info, or a server that no longer works? Open an issue using the [issue template](.github/ISSUE_TEMPLATE/add_server.md).

## Code of Conduct

Be respectful, constructive, and welcoming. We're all here to make AI coding better.

## Questions?

Open an issue with the "question" label. We're happy to help.
