---
title: Viewing stats and console in Discord
slug: viewing-stats-and-console-in-discord
description: Check player counts, performance, and server output from Discord.
---

Beyond powering the server on and off, the bot lets you keep an eye on how it's doing
— player counts, resource usage, and recent output — right inside Discord. Great for
a quick health check without opening the panel.

## Check server status

A **status** command shows the essentials at a glance:

- **Online or offline**
- **Players connected** (and often the max)
- **Resource usage** — CPU and memory
- Sometimes **uptime** and the current version

Run it any time you want a quick pulse on the server. The exact command is in *Bot
commands reference*.

## Player counts

For a community server, live player numbers are handy:

- See **who's on** and how many, on demand.
- Some setups can show the count in a **channel name or the bot's status**, so it's
  visible without running a command.

This is a nice touch for public servers — members can see at a glance whether it's
worth hopping on.

## Resource usage

The bot can surface the same **CPU and memory** figures you'd see in the panel. Watch
these to spot trouble early:

- **Memory creeping toward the limit** → schedule a restart (see *Scheduling restarts
  and tasks* in Game Servers).
- **CPU pinned high** → you may be overloaded; see *Reducing lag and monitoring
  resources*.

Pair this with alerts so you're told automatically when a threshold is crossed (see
*Alert thresholds and notifications*).

## Console output

Depending on your setup, the bot can show **recent console output** or forward it to
a channel — useful for spotting errors or watching a server come online after a
restart. For deep debugging you'll still want the full panel console (see *Using the
game panel console* in Game Servers), but a Discord feed is great for keeping an eye
on things.

## Keep it tidy

- **Use a dedicated channel** for status/console output so it doesn't clutter chat.
- **Limit console output to staff channels** — logs can be noisy and occasionally
  reveal detail you'd rather keep internal.
- **Don't over-poll** — constantly spamming status commands adds noise; set up a
  live status message or alerts instead.

## Troubleshooting

- **Stats not showing:** confirm the server is **linked** and the bot is online (see
  *Troubleshooting the bot*).
- **Numbers look wrong/stale:** there can be a short delay; re-run the command. If
  it's persistently wrong, re-link the server.
- **No console output:** console forwarding may not be enabled for your setup — check
  your configuration or open a ticket (see *Opening a support ticket*).
