# Mallow — All-in-one Discord bot

Mallow is a modular Discord.js bot foundation with persistent per-server configuration, moderation, AutoMod, logging, welcome messages, tickets, XP/levels, economy basics and utilities.

## Setup
1. Install Node.js 20+ and run `npm install`.
2. Copy `.env.example` to `.env`. Add your Discord application bot token and application/client ID. Never commit `.env`.
3. In the Discord Developer Portal enable Server Members Intent and Message Content Intent.
4. Run `npm run deploy` to register slash commands. During development, set DEV_GUILD_ID for instant guild command registration.
5. Invite the bot with the `bot` and `applications.commands` scopes and only the permissions required for enabled features.
6. Run `npm start`.
7. In Discord run `/setup` to choose log/welcome channels and a staff role.

## Security
Secrets are environment-only. Sensitive commands use Discord default member permissions plus runtime hierarchy checks. SQLite uses WAL mode for persistence. Give the bot only the permissions it needs and keep its role below owner/admin roles.

## Included now
Moderation: ban, kick, timeout, warn, warnings, purge. AutoMod: spam/mass-mention and optional invite blocking foundation. Logging: deleted/edited messages and moderation/ticket logs. Tickets: private persistent ticket creation with staff access. Welcome, XP/rank, daily economy/balance, utility info, per-guild setup.

## Production notes
For a large multi-instance deployment, migrate SQLite to PostgreSQL and add Redis-backed distributed cooldowns/queues. Back up the database regularly. Test permissions in a staging server before production.

## Roadmap
The architecture/database is prepared to expand into ticket buttons/transcripts, unban/untimeout/clearwarnings/slowmode/lock/unlock, button roles, full shop/inventory, giveaways, polls/suggestions, temporary voice channels, custom commands, richer admin configuration, raid heuristics and additional audit events.
