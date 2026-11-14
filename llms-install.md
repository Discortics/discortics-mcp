# Installing the Discortics MCP Server

Discortics is a hosted remote MCP server. Nothing needs to be installed locally: no binary, package, API key or environment variable.

## Configuration

- **URL**: `https://api.discortics.com/mcp`
- **Transport**: Streamable HTTP
- **Auth**: OAuth 2.0 (PKCE, dynamic client registration). The client discovers it from `https://api.discortics.com/.well-known/oauth-protected-resource/mcp` and opens a browser sign-in with Discord, where the user picks which servers to grant.

```json
{
  "mcpServers": {
    "discortics": {
      "type": "streamable-http",
      "url": "https://api.discortics.com/mcp"
    }
  }
}
```

Claude Code: `claude mcp add --transport http discortics https://api.discortics.com/mcp`

## Prerequisites

The user must administer the Discord server and have the Discortics bot invited to it: https://discortics.com/invite

## Verify

After sign-in, call `list_servers`. It returns the servers granted in this connection. Server changes are only applied after the user confirms a proposal in chat.
