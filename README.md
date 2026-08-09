# Zernio Plugin (Claude Code, Codex CLI, Antigravity CLI)

Schedule, publish, and analyze social media across 16 platforms (Instagram, TikTok, YouTube, X, LinkedIn, Facebook, Threads, Pinterest, Reddit, Bluesky, WhatsApp, Telegram, Snapchat, Google Business, Discord, Slack) directly from Claude Code, Codex CLI, and Antigravity CLI / Gemini CLI, plus a unified inbox, paid-ads management, and analytics. Powered by Zernio's hosted MCP server (300+ tools).

## Install

### Claude Code

```bash
# Direct plugin marketplace install
/plugin marketplace add salemaziel/zernio-claude-plugin
/plugin install zernio-claude-plugin@zernio-claude-plugin

# Or via VDW Plugin Marketplace
claude plugin install vdw/zernio-claude-plugin
```

### Codex CLI

```bash
# Via VDW Marketplace
codex plugin add zernio-claude-plugin@vdw
```

### Antigravity CLI / Gemini CLI

```bash
# Via VDW Extension Registry
gemini extension install vdw-claude-plugins/zernio-claude-plugin
```

Then authenticate the **zernio** MCP server when prompted or via your CLI's MCP login command (`/mcp` or `codex mcp login zernio`). Your browser opens the Zernio consent screen, you approve, and the CLI stores the token. There's no API key to copy.

Already have a Zernio account? That's the one you sign in with. If you don't, create it during the flow.

## What you can do

- "List my connected social accounts" (`/accounts` or `/zernio:accounts`)
- "Schedule a LinkedIn post for tomorrow at 9am: ..."
- "Cross-post this to X, LinkedIn, and Bluesky right now"
- "Show my unread Instagram DMs"
- "What's the best time to post this week?"
- "List my active Meta ad campaigns and their spend"

## How it works

This plugin bundles a single remote MCP server, `https://mcp.zernio.com/mcp` (Streamable HTTP), authenticated with OAuth 2.0 (PKCE). No local install or Python required, and the tool list comes from the server, so new Zernio endpoints show up without updating the plugin.

Tokens are short-lived and refresh automatically. Revoke access any time from [zernio.com/dashboard](https://zernio.com/dashboard); that kills this client alone and leaves your API keys and other integrations untouched.

### Headless and CI

Headless runs can't open a browser, so a machine that has never signed in can't complete OAuth. Two options:

- Sign in once interactively on that machine (`claude mcp login zernio` / `codex mcp login zernio`). The stored token refreshes on its own from then on.
- Or skip the plugin and configure the server with an API key, which needs no browser:

  ```bash
  claude mcp add --transport http zernio https://mcp.zernio.com/mcp \
    --header "Authorization: Bearer sk_your_key"
  ```

  Create a key at [zernio.com/dashboard/api-keys](https://zernio.com/dashboard/api-keys).

## Links

- Docs: https://docs.zernio.com/resources/mcp
- Dashboard: https://zernio.com/dashboard
- Support: support@zernio.com

