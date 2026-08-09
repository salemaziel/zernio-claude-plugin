# zernio-claude-plugin

Schedule, publish, and analyze social media across 15+ platforms (Instagram, TikTok, YouTube, X, LinkedIn, Facebook, Threads, Pinterest, Reddit, Bluesky, WhatsApp, Telegram, Snapchat, Google Business, Discord, Slack) directly from Antigravity CLI and Gemini CLI, plus a unified inbox, paid-ads management, and analytics. Powered by Zernio's hosted MCP server (300+ tools).

Antigravity CLI & Gemini CLI native plugin for Zernio social media automation. When a task requires social media scheduling, cross-posting, inbox response, campaign reporting, or analytics, read this guidance and use the registered Zernio MCP tools.

## Commands

- **/accounts** (`/zernio:accounts`): List your connected Zernio social media accounts and a quick activity summary.

## MCP Server Integration

This plugin connects to Zernio's hosted MCP server:
- **Server Name**: `zernio`
- **Transport**: `http` (OAuth 2.0 PKCE)
- **URL**: `https://mcp.zernio.com/mcp`

## Core Capabilities & Tool Workflows

1. **Account Orientation & Status**:
   - Call `accounts_list` to list connected accounts across platforms (platform, username, ID).
   - Verify active tokens and connection health.

2. **Publishing & Scheduling**:
   - Call `posts_create` or `posts_schedule` to publish or queue posts for single or multiple platforms.
   - Call `posts_list` to retrieve upcoming scheduled posts and recent publications.

3. **Unified Social Inbox**:
   - Query incoming messages, comments, and direct messages across platforms.
   - Reply to user interactions directly via inbox tools.

4. **Analytics & Performance Insights**:
   - Retrieve engagement metrics, best posting times, top performing posts, and follower growth trends.

5. **Ad Campaigns & Paid Spend**:
   - Inspect active paid ad campaigns (e.g. Meta ads), budgets, and spend reports.
