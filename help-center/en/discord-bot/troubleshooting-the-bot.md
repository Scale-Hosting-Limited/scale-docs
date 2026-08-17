---
title: Troubleshooting the bot
slug: troubleshooting-the-bot
description: Fix the bot when it's offline, ignoring commands, or not posting alerts.
---

If the Scale Discord bot isn't behaving, it's usually one of a handful of causes —
permissions, linking, or the bot being offline. Work through these and you'll fix
most problems quickly.

## The bot is offline in Discord

If the bot shows offline in your member list:

- **Check our status** — a platform issue may be affecting the bot (see *Scheduled
  maintenance and status*).
- **Re-invite it** if it was removed — see *Adding the bot to your server*.
- **Wait a moment** after adding it; it can take a short while to appear online.

If the bot is offline, no commands or alerts will work until it's back.

## Commands do nothing

The most common issue. Check, in order:

1. **Permissions** — does your Discord **role** allow that command? Power commands
   should be limited to admins/mods (see *Setting up permissions and roles*).
2. **Channel permissions** — can the bot **read and send** in that channel? It needs
   the right Discord channel permissions.
3. **Server linked?** — the bot must be **linked** to your game server to control it
   (see *Linking your game server*).
4. **Right command/syntax** — check the exact command in *Bot commands reference*.

## Commands work but nothing happens on the server

If the bot accepts the command but the server doesn't react:

- The **link may have broken** — re-link the server in your panel.
- The **server may be mid-action** (already starting/stopping) — wait and re-check
  status.
- The **server itself may be stuck** — check the panel console (see *Server won't
  start*).

## Not receiving alerts

- **Alerts enabled?** Confirm the events you want are turned on (see *Alert
  thresholds and notifications*).
- **Channel set and accessible?** The bot needs permission to post in the alert
  channel.
- **Thresholds too high?** You won't get resource alerts if the threshold is never
  reached.
- **Bot online?** It can't send alerts while offline.

## Status/stats look wrong

- **Stale numbers:** re-run the command; there can be a brief delay.
- **Persistently wrong:** re-link the server so the bot refreshes what it's watching.

## Bot was working, now it isn't

Ask what changed:

- **Discord permissions or roles** were edited → recheck them.
- **The server was reinstalled/changed** → re-link it.
- **The bot was removed and re-added** → reconfigure permissions and linking.

## Still stuck?

Open a ticket (see *Opening a support ticket*) with:

- **What's not working** (offline / command X does nothing / no alerts).
- **What you've tried** from this guide.
- The **command** you're running and **your role**.
- Whether the **server is linked** and the **bot shows online**.

That's enough for us to pinpoint it fast.
