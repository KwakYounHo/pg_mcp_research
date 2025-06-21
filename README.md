# K_YH mcp-db-server

## Introduction

> This package is purely experimental and just for fun!

**Do not use this code in production or with any critical databases.**

This implementation grants full control over the database to the agent.
Therefore, it is **strongly discouraged** to use shared or sensitive databases.

## References

This implementation is based on the [mcp/postgres](https://hub.docker.com/r/mcp/postgres) Docker image.

- [Docker Image on Docker Hub](https://hub.docker.com/r/mcp/postgres)
- [Source Code on GitHub](https://github.com/modelcontextprotocol/servers/blob/2025.4.24/src/postgres/index.ts)

## Usage

```bash
npx @k_yh/mcp-db-server <your-postgresql-url>
```

For example:

```bash
npx @k_yh/mcp-db-server 'postgresql://user:password@127.0.0.1:5432/my-db'
```

To use this with an agent like `Claude desktop` or `Cursor`, configure it like so:

```json
{
  "mcpServers": {
    "my-db-server": {
      "command": "npx",
      "args": [
        "-y",
        "@k_yh/mcp-db-server",
        "postgresql://user:password@localhost:5432/my-db"
      ]
    }
  }
}
```

You can manipulate the database through the agent using your prompt.
