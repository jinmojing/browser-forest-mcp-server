# Browser Forest MCP Server

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Anti-detect cloud browser for AI agents.** Browser Forest is a cloud browser API built on a **kernel-patched Chromium** (31 Chromium + 4 V8 patches). The anti-detect engine lives in the browser core — not in proxies or UA spoofing — so agents can browse, extract, and automate where plain Playwright/browserless get blocked.

- 🛡️ **Bypasses DataDome / PerimeterX / Cloudflare** — verified against 216 sites (111 collectable, including Amazon×4, Walmart, Booking, Indeed)
- 🤖 **AI behavior layer (BG engine)** — human-like clicks with real trajectories (`isTrusted` + trace), trusted form filling
- 🔎 **Perception → action loop** — `bf_snapshot` (AX tree + refs) feeds `bf_click`/`bf_fill`
- 🖥️ **Live View** debugging, session recording/replay, multi-tab support
- 🔌 **MCP Streamable HTTP** — works with Claude Desktop, Cursor, Windsurf, and any MCP client

## Quick Start

This is a **remote MCP server** — no local install needed. Point your MCP client at:

```
https://browserforest.com/api/mcp/bf
```

You need an **API key** (`bf_live_...`). Generate one from the [Browser Forest dashboard](https://browserforest.com/dashboard/keys).

### Claude Desktop

```json
{
  "mcpServers": {
    "browser-forest": {
      "url": "https://browserforest.com/api/mcp/bf",
      "headers": { "X-API-Key": "bf_live_xxx" }
    }
  }
}
```

### Python (SDK)

```bash
pip install browser-forest
```

## Tools

| Tool | Description |
|---|---|
| `bf_create_session` | Create an anti-detect browser session (url/proxy/contextId) |
| `bf_navigate` | Navigate + wait for load |
| `bf_extract` | Extract page content by selector |
| `bf_screenshot` | Screenshot current page (base64 PNG) |
| `bf_click` | Click with AI behavior engine (human trajectory) |
| `bf_fill` | Fill forms with AI behavior engine |
| `bf_scroll` | Scroll the page |
| `bf_snapshot` | Accessibility snapshot (AX tree + refs) |
| `bf_close` | Close the session |

## Why Browser Forest?

Most "anti-detect" services are proxy + UA fingerprint hacks — easy to fingerprint and block. Browser Forest patches the browser kernel itself (31 Chromium + 4 V8 patches), so the browser *is* undetectable: consistent fingerprint, no automation leaks, works against aggressive bot managers.

## Links

- [Website](https://browserforest.com)
- [API Docs](https://browserforest.com/api/docs)
- [Dashboard](https://browserforest.com/dashboard/keys)

## License

MIT
