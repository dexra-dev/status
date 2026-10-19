# Dexra status checks

Every five minutes GitHub Actions checks, from outside the server:

- `https://api.dexra.dev/health` — the API
- `POST https://api.dexra.dev/mcp` `tools/list` — the MCP endpoint
- `https://dexra.dev/` — the site

A check fails after three failed tries 20 seconds apart. Then an issue labelled `outage` opens; it closes by itself, with how long it lasted, when every check passes again. [Open outages](../../issues?q=label%3Aoutage), [past ones](../../issues?q=label%3Aoutage+is%3Aclosed).

Uptime by day, measured by the server's own heartbeat: [dexra.dev/status](https://dexra.dev/status).

Telegram alerts: set the repository secrets `TELEGRAM_BOT_TOKEN` and `TELEGRAM_CHAT_ID`. Who gets assigned: the `ASSIGNEE` variable (default `oblivisheee`).
