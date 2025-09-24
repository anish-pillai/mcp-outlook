# Outlook MCP Python Client (Minimal)

## Prereqs
- Put Outlook app creds in `outlook-mcp/.env`:
  - `OUTLOOK_CLIENT_ID=...`
  - `OUTLOOK_CLIENT_SECRET=...`
- Put your Anthropic key in this folder’s `.env`:
  - `ANTHROPIC_API_KEY=...`

## Run
```bash
# from outlook-mcp-client/
uv run client.py ./server/index.js
# or
python client.py ./server/index.js
```
Then complete the Microsoft login in your browser. Tokens are saved to `~/.outlook-mcp-tokens.json`.

Type queries in the console. Type `quit` to exit.