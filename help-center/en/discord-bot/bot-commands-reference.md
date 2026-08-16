---
title: Bot commands reference
slug: bot-commands-reference
description: The commands the Scale Discord bot supports and what each one does.
---

Once the bot is added and linked to a server (see *Adding the bot* and *Linking
your game server*), you and your community can run these from Discord. The exact
set depends on the abilities you've enabled for the link.

## Status & info

- **`/status`** — shows whether the linked server is online, and the current player
  count.
- **`/players`** — lists who's currently online (where supported by the game).
- **`/address`** — shows the server's connection address so members can copy it.
- **`/info`** — the server's name, type, and status at a glance.

## Power actions (permission-gated)

These map to real actions and are only available to roles you allow:

- **`/start`** — start the server if it's off.
- **`/restart`** — restart it (useful after a config change).
- **`/stop`** — stop it.

Power actions always respect the panel's own permissions — the bot is never a way
around them.

## Setup & admin

- **`/link <code>`** — pair this Discord to a server using a code from the panel.
- **`/unlink`** — remove the link.
- **`/settings`** — view or change which channel the bot posts in and which
  abilities are enabled.
- **`/help`** — list the commands available to you here.

## Notes

- Command availability depends on the **abilities** granted to the link and the
  **Discord role** of the person running them — a member may see `/status` but not
  `/restart`.
- If a command doesn't appear, the bot may lack permission in that channel, or the
  ability isn't enabled for the link. See *Setting up permissions and roles* and
  *Troubleshooting the bot*.
- Slash commands can take a moment to appear after the bot is first added while
  Discord registers them.
