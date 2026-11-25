# Pivlu App Database (MCP server)

<img src="assets/logo.svg" width="72" alt="Pivlu logo">

[![Pivlu App Database MCP connector](https://glama.ai/mcp/connectors/com.pivlu/app-database/badges/score.svg)](https://glama.ai/mcp/connectors/com.pivlu/app-database)

Estimated monthly revenue and chart ranks for 10,000+ App Store apps, plus breakout directions, playbooks and fast-rising GitHub repos, in any MCP client. Hosted by Pivlu: free, read-only, nothing to install.

- **Endpoint:** `https://pivlu.com/mcp` (Streamable HTTP, OAuth 2.1 with discovery, dynamic client registration and PKCE)
- **Official MCP Registry:** `com.pivlu/app-database`
- **Glama:** https://glama.ai/mcp/connectors/com.pivlu/app-database
- **Website:** https://pivlu.com/en/start/ (中文: https://pivlu.com/start/)

Pivlu takes a daily snapshot of the App Store free, paid and top-grossing charts in 150 countries and regions, and estimates each charting app's monthly revenue from its chart ranks.

## What you can ask

- Roughly how much an app makes per month (an estimate, with a range), where it charts, its best rank, days since launch, rating count and developer
- Apps filtered by genre, country or days since launch, sorted by estimated monthly revenue
- Today's top apps on one country's free, paid or top-grossing chart
- The daily pulse: newly rising apps and fast-rising GitHub repos
- Pivlu's write-ups on market directions, playbooks and individual products

Example prompts:

- "Using Pivlu: among productivity apps launched in the last 90 days, which 5 have the highest estimated monthly revenue, and who makes them?"
- "What are today's top 10 apps on Japan's top-grossing App Store chart?"
- "Look up the app Calm: estimated monthly revenue, which countries it charts in, and its best rank."
- "Which new GitHub repos are gaining stars fastest right now?"

## Connect

Clients that support remote MCP servers with OAuth only need the URL `https://pivlu.com/mcp`. The first time, a Pivlu sign-in page opens (Google or an emailed 6-digit code, free); click **Allow**.

**Claude Code**

```bash
claude mcp add --transport http pivlu https://pivlu.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`)

```json
{"mcpServers": {"pivlu": {"url": "https://pivlu.com/mcp"}}}
```

**VS Code** (`.vscode/mcp.json`)

```json
{"servers": {"pivlu": {"type": "http", "url": "https://pivlu.com/mcp"}}}
```

**ChatGPT, Claude (web and desktop), Grok, Kimi Work and other apps with connectors or custom plugins:** add a custom connector with the URL `https://pivlu.com/mcp`, then sign in to Pivlu and click **Allow**.

**Clients without OAuth:** sign in at https://pivlu.com/en/start/ and copy your personal address `https://pivlu.com/mcp/<your-key>` (Streamable HTTP). SSE-only clients use `https://pivlu.com/sse/<your-key>`. The key is your account credential, so keep it private.

Setup notes for many more clients: https://pivlu.com/connect.md

## Tools

All 10 tools are read-only (`readOnlyHint: true`) and change nothing in your account.

| Tool | What it does |
|---|---|
| `search` | Search Pivlu's published apps, investigations, playbooks and directions |
| `fetch` | Read a full page, or all data for one app by its id |
| `apps` | Query the app library: filter by name, country, genre or days since launch; sort by estimated monthly revenue (USD, with a range), days since launch, best rank or rating count |
| `app_lookup` | All fields for one app by its id |
| `hot` | Top apps on one country's free, paid or top-grossing chart |
| `feed` | Daily pulse: apps and repos that just appeared or moved a lot |
| `directions` | Market directions Pivlu tracks, with how many apps cross the line today |
| `plays` | Search playbooks only |
| `story` | Search investigations only |
| `github` | Fast-rising GitHub repos, optionally new ones only |

## Good to know

- Revenue figures are estimates based on chart rank, not data from store accounts.
- App Store only (no Google Play) and no download numbers. Only apps that have appeared on the tracked charts are included.
- Free. Each account gets 200 calls per day.
- Privacy: https://pivlu.com/en/privacy/ · Terms: https://pivlu.com/en/terms/ · Contact: support@pivlu.com

This repository holds connection docs and listing metadata (`server.json`, `mcp.json`, `.mcp.json`, `.cursor-plugin/plugin.json`). The server itself is hosted by Pivlu.

## 中文说明

Pivlu 应用数据库：一万多个苹果商店应用的估算月收入和各国榜单名次，还有过线方向、打法和 GitHub 热门项目。免费，每个账号每天 200 次；10 个工具全部只读。

- 支持 OAuth 的客户端（Claude、ChatGPT、Kimi Work 等）：地址填 `https://pivlu.com/mcp`，第一次用会跳到 Pivlu 登录（谷歌账号或邮箱验证码），点“允许”。
- 只能填固定地址的客户端：在 https://pivlu.com/start/ 登录，复制专属地址 `https://pivlu.com/mcp/<钥匙>`；只支持 SSE 的用 `https://pivlu.com/sse/<钥匙>`。钥匙就是账号凭证，别公开。
- 收入是按榜单名次估算的，不是商店后台数据；只有苹果商店，没有下载量。
- 各家客户端的填法：https://pivlu.com/connect.md
- 隐私政策 https://pivlu.com/privacy/ · 服务条款 https://pivlu.com/terms/ · 联系 support@pivlu.com
# Pivlu App Database (MCP server)

<img src="assets/logo.svg" width="72" alt="Pivlu logo">

Estimated monthly revenue and chart ranks for 10,000+ App Store apps, plus breakout directions, playbooks and fast-rising GitHub repos, in any MCP client. Hosted by Pivlu: free, read-only, nothing to install.

- **Endpoint:** `https://pivlu.com/mcp` (Streamable HTTP, OAuth 2.1 with discovery, dynamic client registration and PKCE)
- **Official MCP Registry:** `com.pivlu/app-database`
- **Website:** https://pivlu.com/en/start/ (中文: https://pivlu.com/start/)

Pivlu takes a daily snapshot of the App Store free, paid and top-grossing charts in 150 countries and regions, and estimates each charting app's monthly revenue from its chart ranks.

## What you can ask

- Roughly how much an app makes per month (an estimate, with a range), where it charts, its best rank, days since launch, rating count and developer
- Apps filtered by genre, country or days since launch, sorted by estimated monthly revenue
- Today's top apps on one country's free, paid or top-grossing chart
- The daily pulse: newly rising apps and fast-rising GitHub repos
- Pivlu's write-ups on market directions, playbooks and individual products

Example prompts:

- "Using Pivlu: among productivity apps launched in the last 90 days, which 5 have the highest estimated monthly revenue, and who makes them?"
- "What are today's top 10 apps on Japan's top-grossing App Store chart?"
- "Look up the app Calm: estimated monthly revenue, which countries it charts in, and its best rank."
- "Which new GitHub repos are gaining stars fastest right now?"

## Connect

Clients that support remote MCP servers with OAuth only need the URL `https://pivlu.com/mcp`. The first time, a Pivlu sign-in page opens (Google or an emailed 6-digit code, free); click **Allow**.

**Claude Code**

```bash
claude mcp add --transport http pivlu https://pivlu.com/mcp
```

**Cursor** (`~/.cursor/mcp.json`)

```json
{"mcpServers": {"pivlu": {"url": "https://pivlu.com/mcp"}}}
```

**VS Code** (`.vscode/mcp.json`)

```json
{"servers": {"pivlu": {"type": "http", "url": "https://pivlu.com/mcp"}}}
```

**ChatGPT, Claude (web and desktop), Grok, Kimi Work and other apps with connectors or custom plugins:** add a custom connector with the URL `https://pivlu.com/mcp`, then sign in to Pivlu and click **Allow**.

**Clients without OAuth:** sign in at https://pivlu.com/en/start/ and copy your personal address `https://pivlu.com/mcp/<your-key>` (Streamable HTTP). SSE-only clients use `https://pivlu.com/sse/<your-key>`. The key is your account credential, so keep it private.

Setup notes for many more clients: https://pivlu.com/connect.md

## Tools

All 10 tools are read-only (`readOnlyHint: true`) and change nothing in your account.

| Tool | What it does |
|---|---|
| `search` | Search Pivlu's published apps, investigations, playbooks and directions |
| `fetch` | Read a full page, or all data for one app by its id |
| `apps` | Query the app library: filter by name, country, genre or days since launch; sort by estimated monthly revenue (USD, with a range), days since launch, best rank or rating count |
| `app_lookup` | All fields for one app by its id |
| `hot` | Top apps on one country's free, paid or top-grossing chart |
| `feed` | Daily pulse: apps and repos that just appeared or moved a lot |
| `directions` | Market directions Pivlu tracks, with how many apps cross the line today |
| `plays` | Search playbooks only |
| `story` | Search investigations only |
| `github` | Fast-rising GitHub repos, optionally new ones only |

## Good to know

- Revenue figures are estimates based on chart rank, not data from store accounts.
- App Store only (no Google Play) and no download numbers. Only apps that have appeared on the tracked charts are included.
- Free. Each account gets 200 calls per day.
- Privacy: https://pivlu.com/en/privacy/ · Terms: https://pivlu.com/en/terms/ · Contact: support@pivlu.com

This repository holds connection docs and listing metadata (`server.json`, `mcp.json`, `.mcp.json`, `.cursor-plugin/plugin.json`). The server itself is hosted by Pivlu.

## 中文说明

Pivlu 应用数据库：一万多个苹果商店应用的估算月收入和各国榜单名次，还有过线方向、打法和 GitHub 热门项目。免费，每个账号每天 200 次；10 个工具全部只读。

- 支持 OAuth 的客户端（Claude、ChatGPT、Kimi Work 等）：地址填 `https://pivlu.com/mcp`，第一次用会跳到 Pivlu 登录（谷歌账号或邮箱验证码），点“允许”。
- 只能填固定地址的客户端：在 https://pivlu.com/start/ 登录，复制专属地址 `https://pivlu.com/mcp/<钥匙>`；只支持 SSE 的用 `https://pivlu.com/sse/<钥匙>`。钥匙就是账号凭证，别公开。
- 收入是按榜单名次估算的，不是商店后台数据；只有苹果商店，没有下载量。
- 各家客户端的填法：https://pivlu.com/connect.md
- 隐私政策 https://pivlu.com/privacy/ · 服务条款 https://pivlu.com/terms/ · 联系 support@pivlu.com
