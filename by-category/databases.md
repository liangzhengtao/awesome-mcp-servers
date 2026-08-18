# 🗄️ Databases

MCP servers for database access — query, explore, cache, and manage your data layer.

## Servers

| Server | Description | Package | Status |
|--------|-------------|---------|--------|
| [PostgreSQL](../servers/postgres.md) | Query and explore PostgreSQL databases | `@modelcontextprotocol/server-postgres` | Stable |
| [Redis](../servers/redis.md) | Cache, pub/sub, and key-value operations | `@modelcontextprotocol/server-redis` | Stable |

## Typical Workflows

### Database Exploration

1. **PostgreSQL** — List schemas and tables
2. **PostgreSQL** — Run analytical queries
3. **Filesystem** — Generate migration scripts

### Performance Debugging

1. **PostgreSQL** — Check slow query stats
2. **Redis** — Inspect cache hit rates
3. Identify missing indexes or cache opportunities

### Building a New Feature

1. **PostgreSQL** — Explore existing schema
2. **PostgreSQL** — Draft and test migration queries
3. **Redis** — Set up caching layer
4. **Filesystem** — Update ORM models

## Security Proven Patterns

- Use **read-only** database connections for production
- Create **dedicated users** with minimal permissions
- Never store connection strings with passwords in version control
- Use environment variables for all credentials
- Prefer **local/VPN** connections over public endpoints

## See Also

- [Development](development.md) — For code and container management
- [Communication](communication.md) — For team collaboration
