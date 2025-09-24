# MCP Outlook (Monorepo)

Minimal setup to run an Outlook MCP Server and a Python MCP Client in one repo.

## Structure

- `server/` – Outlook MCP Server (subtree of upstream repo)
- `client-py/` – Python client that connects to the server

## Prerequisites

- Node.js (for the server)
- Python 3.11+ (for the client) – `uv` recommended
- Azure App Registration for Microsoft Graph

## Configure

- In `server/.env` set:
  - `OUTLOOK_CLIENT_ID=...`
  - `OUTLOOK_CLIENT_SECRET=...`
- In `client-py/.env` set:
  - `ANTHROPIC_API_KEY=...`

## Run (Server)

From `server/`:

```bash
pnpm i
pnpm run auth-server   # starts auth helper on http://localhost:3333 (leave running)
pnpm start             # starts MCP server over stdio
```

## Run (Python Client)

From `client-py/`:

```bash
uv run client.py ./server/index.js
# or
python client.py ./server/index.js
```

Complete Microsoft login in your browser when prompted. Tokens are stored at `~/.outlook-mcp-tokens.json`.

Type queries in the console; type `quit` to exit.

## Update server subtree (optional)

If `server/` was added via git subtree:

```bash
git fetch outlook-upstream
git subtree pull --prefix server outlook-upstream main --squash
```
