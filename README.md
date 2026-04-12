# Discord.js Verification Bot

Verification bot with slash subcommands, captcha-based onboarding, local JSON storage, and component v2 UI for setup, config, stats, and panel messages.

<img width="600" height="235" alt="image (1)" src="https://github.com/user-attachments/assets/ef5336cb-b7bb-4b58-a85e-2f020839e954" />

Copyright (c) Cortex Realm  
Server Url: https://discord.gg/EWr3GgP6fe

## Features

- `/verify setup` to save the verified role, panel channel, and optional log channel
- `/verify panel` to send a verification panel with a button
- `/verify settings` to control captcha length, timeout, max attempts, and enabled state
- `/verify config` to view current guild settings
- `/verify stats` to view guild totals or a member's current verification state
- `/verify reset` to clear a member's active challenge and optionally remove the verified role
- captcha image flow with refresh support and modal answer input
- local JSON database with queued writes, audit entries, and guild stats

## Requirements

- Node.js `20.11.0` or newer
- A Discord bot with these gateway intents enabled:
  - `Guilds`
  - `GuildMembers`

## Setup

1. Create a bot in the Discord Developer Portal.
2. Enable the `SERVER MEMBERS INTENT`.
3. Invite the bot with `bot` and `applications.commands` scopes.
4. Make sure the bot role is above the verified role in your server.
5. Copy `.env.example` to `.env` and fill in the values.

## Install

```bash
npm install
```

## Start

```bash
npm start
```

Commands deploy automatically when the bot logs in.

Commands deploy globally and can take some time to fully appear across Discord.

## First-Time Discord Setup

Run these commands in your server after the bot is online:

```text
/verify setup role:@Verified channel:#verify-panel log-channel:#logs
/verify settings captcha-length:6 timeout-minutes:5 max-attempts:3 enabled:true
/verify panel channel:#verify-panel
```

## Command Reference

```text
/verify setup
/verify settings
/verify panel
/verify config
/verify stats
/verify reset
```

## Notes

- The bot stores data in `data/database.json` by default.
- Captcha challenges are ephemeral and expire automatically.
- If role assignment fails, check bot permissions and role order.
