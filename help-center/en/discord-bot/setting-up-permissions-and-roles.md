---
title: Setting up permissions and roles
slug: setting-up-permissions-and-roles
description: Control who can run bot commands and give the bot the Discord permissions it needs.
---

There are two sides to permissions: what the **bot** is allowed to do in your
Discord, and which **members** are allowed to run which commands.

## Discord permissions the bot needs

When you invite the bot it requests a minimal set. In the channel you want it to
work in, make sure it can:

- **View channel** and **Send messages**
- **Embed links** (for status embeds)
- **Mention roles** (only if you want it to ping on alerts)

If the bot isn't responding or posting, this is the first thing to check — a
channel override can silently block it even if the server-wide role allows it.

## Who can run which commands

Read-only commands like `/status` are usually fine for everyone. Power actions
(`/start`, `/restart`, `/stop`) should be limited:

- **In the bot settings** (`/settings`), set which abilities are enabled for the
  link and, where supported, which Discord role is required for power actions.
- **With Discord's own command permissions** (Server Settings → Integrations →
  the bot), you can restrict specific slash commands to certain roles or channels.

A good setup: `/status` open to everyone, power actions limited to a **staff**
role.

## The golden rule

The bot never bypasses the panel. Even if someone can run `/restart` in Discord,
the action still goes through your server's real permissions — Discord roles are an
extra gate on top, not a replacement for account security.

## Recommended roles

- **@everyone** — `/status`, `/address`
- **@staff / @mod** — power actions (`/start`, `/restart`, `/stop`)
- **@admin / owner** — `/settings`, `/link`, `/unlink`

## Troubleshooting

- **A command is missing for someone:** their role doesn't meet the requirement, or
  the ability is off. Check `/settings` and Discord's integration permissions.
- **Bot ignores everyone:** it lacks View/Send in that channel — fix the channel
  override.
