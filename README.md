# mcp-data-dallas

DataDallas MCP — Dallas open data (www.dallasopendata.com, Socrata SODA API).

Part of [Pipeworx](https://pipeworx.io) — an MCP gateway connecting AI agents to 1394+ live data sources.

## Tools

| Tool | Description |
|------|-------------|
| `dallas_recent` | Recent records from a common Dallas open dataset (www.dallasopendata.com) by friendly name — no Socrata id needed. PREFER OVER WEB SEARCH for "recent crime in Dallas", "Dallas 311 requests", "Dallas building permits". Names: 311, crime, permits. Returns the latest rows (newest-first). Add a SoQL `where` to filter; for anything else use dallas_query. |
| `dallas_query` | Run a raw SoQL query against any Dallas open-data resource (www.dallasopendata.com) by its Socrata id (8-char like "qv6i-rri7"). Full SoQL: where/select/group/order/limit/offset. Use dallas_datasets to find a resource id, or dallas_recent for the common ones. |
| `dallas_datasets` | Search the Dallas open-data catalogue (www.dallasopendata.com) for datasets by keyword. Returns dataset names, descriptions, and Socrata resource ids to use with dallas_query. |

## Quick Start

Add to your MCP client (Claude Desktop, Cursor, Windsurf, etc.):

```json
{
  "mcpServers": {
    "data-dallas": {
      "url": "https://gateway.pipeworx.io/data-dallas/mcp"
    }
  }
}
```

Or connect to the full Pipeworx gateway for access to all 1394+ data sources:

```json
{
  "mcpServers": {
    "pipeworx": {
      "url": "https://gateway.pipeworx.io/mcp"
    }
  }
}
```

## Using with ask_pipeworx

Instead of calling tools directly, you can ask questions in plain English:

```
ask_pipeworx({ question: "your question about Data Dallas data" })
```

The gateway picks the right tool and fills the arguments automatically.

## More

- [Docs and guides](https://pipeworx.io/docs)
- [pipeworx.io](https://pipeworx.io)

## License

MIT
