# Installing the Dodil MCP server

Dodil is a hosted remote MCP server; there is no package to install.

Add this server to the MCP settings:

```json
{
  "mcpServers": {
    "dodil": {
      "type": "streamableHttp",
      "url": "https://mcp.dodil.io"
    }
  }
}
```

The first tool call opens Dodil's sign-in page (connect.dodil.io) in the
browser. The user signs in and chooses the organizations to grant. No API key
is needed.

To check the connection, call `auth_orgs`: it lists the organizations this
connection can act in.
