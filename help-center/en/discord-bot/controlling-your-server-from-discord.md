---
title: Controlling your server from Discord
slug: controlling-your-server-from-discord
description: Start, stop, and restart your game server with bot commands.
---

Once the bot is linked, you can power your server up and down straight from Discord —
handy for a quick restart from your phone, or letting a trusted mod restart without a
panel login. Here's how, and how to keep it safe.

## Before you start

Make sure you've:

1. **Added the bot** and **linked your server** (see *Adding the bot to your server*
   and *Linking your game server*).
2. **Set permissions** so only trusted roles can run power commands — this is
   important, since these commands affect everyone on the server (see *Setting up
   permissions and roles*).

## Power commands

The bot provides commands to:

- **Start** — boot the server if it's offline.
- **Restart** — stop and start it; use after config or plugin changes.
- **Stop** — shut it down gracefully.

Exact command names and syntax are in *Bot commands reference*. In most cases you run
them in a channel the bot watches, and it reports back the result.

## Restart etiquette

A restart disconnects everyone, so:

- **Warn players first** — post a heads-up, or use a command that announces the
  restart in-game if available.
- **Pick a quiet moment** where you can.
- **Automate routine restarts** on the panel instead of doing them by hand — a daily
  scheduled restart keeps performance healthy (see *Scheduling restarts and tasks*
  in Game Servers).

## Watch it come back

After a start or restart:

- The bot can report when the server is **back online**.
- Check **status** to confirm it's up and accepting players (see *Viewing stats and
  console in Discord*).
- If it doesn't come back, something's wrong on startup — check the panel console
  (see *Server won't start*).

## Keep it secure

These are powerful commands, so:

- **Restrict power commands to admin/mod roles** only (see *Setting up permissions
  and roles*).
- **Use them in a staff channel**, not a public one, so random members can't spam
  them.
- **Review who has the roles** that can control the server, periodically.

A public "restart" command anyone can hit is a recipe for trouble — lock it down.

## Troubleshooting

- **Command does nothing:** confirm your role has permission and the server is linked;
  see *Troubleshooting the bot*.
- **"Server not responding":** it may already be starting/stopping — wait, then check
  status.
- **Won't come back online:** the issue is on the server itself — check the panel
  console and see *Server won't start*.
- **Bot offline:** it can't run commands if the bot itself is down — see
  *Troubleshooting the bot*.
