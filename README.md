# Discortics MCP Server

Official Model Context Protocol (MCP) connector and agent skill bundle for [Discortics](https://discortics.com). Architect, configure, and automate Discord servers, channels, permissions, roles, verification gates, tickets, and security shields directly from your AI agent conversations.

[![Model Context Protocol](https://img.shields.io/badge/MCP-Streamable%20HTTP-green.svg)](https://modelcontextprotocol.io)
[![Status](https://img.shields.io/badge/Status-Production%20Ready-success.svg)](https://discortics.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

---

## 🌟 Overview

The **Discortics MCP Server** connects AI models (Claude, Cursor, Grok, ChatGPT, Codex, LobeChat) directly to the Discortics orchestration engine over remote **Streamable HTTP**.

Whether starting a brand-new Discord server from a blank slate or upgrading an active community with 50,000+ members, Discortics enables AI agents to:

* **Synthesize Themed Communities**: Turn natural prompts (*"Cozy anime cafe"*, *"Cyberpunk esports clan"*, *"Open-source developer hub"*) into clean category trees, channel topics, unicode styling, and harmonic role palettes.
* **Provision Discord Primitives**: Create categories, channels, cosmetic roles, and private staff lounges with least-privilege permission isolation.
* **Orchestrate 20+ Modules**: Configure Verification gates, Support Tickets, Staff Applications, Button/Dropdown Self-Roles, Welcome/Leave onboarding, Starboards, Leveling, and Economy.
* **Harden Server Security**: Audit settings and configure AntiNuke burst protection and automated AutoPilot spam/raid shields.
* **Enforce Human-in-the-Loop Review**: No live mutations touch Discord without explicit human approval. Every architectural plan generates a cryptographic preview URL (`https://discortics.com/mcp/review/<id>`). The assistant summarizes all changes, presents the preview, and waits for text confirmation in chat before recording approval and applying changes. Zero automated administrator permissions are ever granted.

---

## 🚀 Quickstart & Client Setup

### 1. Cursor

Add the Discortics MCP server to your Cursor configuration (`~/.cursor/mcp.json` or `.cursor/mcp.json`):

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

When you first prompt Cursor, it will initiate the Discord OAuth 2.0 PKCE flow to authorize your server.

---

### 2. Claude Code CLI

Add the connector directly using the Claude CLI:

```bash
claude mcp add discortics https://api.discortics.com/mcp
```

---

### 3. Claude Desktop / Claude Connectors

1. Open **Claude Settings** → **Developer** (or **Connectors**).
2. Click **Add Connector**.
3. Enter the server URL: `https://api.discortics.com/mcp`.
4. Sign in with Discord to grant access to your test server.

---

### 4. LobeHub / LobeChat

In LobeChat settings, install the **Discortics** plugin from the marketplace, or configure a custom remote MCP server pointing to:
- **URL**: `https://api.discortics.com/mcp`
- **Transport**: `Streamable HTTP`

---

### 5. Generic MCP Client (Streamable HTTP)

Point any conformant MCP client to:
* **Endpoint**: `https://api.discortics.com/mcp`
* **Transport**: `Streamable HTTP` (POST JSON-RPC 2.0 + SSE streaming)
* **Auth**: RFC 9470 OAuth Protected Resource (`/.well-known/oauth-protected-resource/mcp`) with OAuth 2.0 PKCE.

---

## 🛠️ Available MCP Tools

| Tool | Type | Description |
| :--- | :--- | :--- |
| `list_servers` | Read-only | List Discord servers authorized in the active OAuth grant |
| `get_setup_context` | Read-only | Read live roles, channels, bot permissions, and tier limits |
| `list_features` | Read-only | Enumerate available Discortics configuration modules |
| `get_feature_guide` | Read-only | Fetch operation schemas, questions, and parameter guides |
| `read_configuration` | Read-only | Retrieve module settings for an authorized guild |
| `audit_configuration` | Read-only | Batch-audit multiple server modules in a single call |
| `propose_setup` | Draft | Create an atomic setup proposal and return a preview URL |
| `get_setup_proposal` | Read-only | Inspect step status and outcomes of a stored proposal |
| `approve_setup_proposal` | Confirmation | Record explicit chat confirmation for the exact proposal hash |
| `apply_setup_proposal` | Execution | Execute approved configuration steps in Discord |

---

## 🧠 Agent Skills

This repository bundles the master **`discord-server-architect`** skill inside [`skills/discord-server-architect/`](skills/discord-server-architect/):

* **Blueprint Synthesis**: Translates natural theme requests into atomic configuration steps.
* **Thematic Blueprints**: Curated blueprints for gaming clans, creator streams, anime cafes, study groups, and tech hubs.
* **Permission Isolation**: Hardened security matrices that prevent accidental public leaks of private staff rooms and ticket transcripts.

---

## 🔒 Safety & Security Invariants

1. **Human Confirmation Mandatory**: Mutations require human review. A proposal must be approved via `approve_setup_proposal` before `apply_setup_proposal` will execute.
2. **Zero Administrator Escalation**: Automated tools create only cosmetic, structural, and support roles. Elevated Administrator permissions remain strictly under manual owner control in Discord.
3. **Atomic Sequencing**: Resource references chain explicitly (`@stepId.roleId`, `@stepId.channelId`) so dependencies resolve reliably in sequence.
4. **No Credential Storage**: The MCP server never receives or handles Discord bot tokens, passwords, or personal credentials.

---

## 📄 License

This repository is licensed under the [MIT License](LICENSE).
