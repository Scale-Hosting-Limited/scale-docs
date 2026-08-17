---
title: Alert thresholds and notifications
slug: alert-thresholds-and-notifications
description: Get pinged when your server goes down or runs hot, before players notice.
---

The best way to hear about a problem is *before* your players do. The bot can watch
your server and ping you in Discord when something needs attention — downtime, high
memory, a crash. Here's how to set it up sensibly.

## What you can be alerted about

- **Server down / back up** — the most important: know the moment it goes offline,
  and when it recovers.
- **High memory** — a warning before an out-of-memory crash (see *Out of memory and
  resource limits*).
- **High CPU** — sustained load that means lag.
- **Crashes / unexpected stops** — so you can jump on a crash loop early (see
  *Recovering from a crash loop*).

This turns "a player DM'd me that it's down" into "the bot told me ten minutes ago."

## Set up alerts

1. Open the bot's **notification/alert** settings (in your panel or via a command —
   see *Configuring status notifications*).
2. Choose **which events** to alert on (downtime is the essential one).
3. Pick the **channel** alerts post to — a staff/alerts channel, not public chat.
4. Set any **thresholds** for resource alerts (below).

## Choosing good thresholds

The art is alerting on real problems without crying wolf:

- **Memory:** alert when it's **consistently high** (say, near the ceiling), not on a
  brief spike. A one-off blip during a busy moment is normal.
- **CPU:** alert on **sustained** high usage, not momentary peaks.
- **Downtime:** alert **immediately** — there's no "false alarm" for a server that's
  actually offline.

Too-sensitive thresholds cause alert fatigue — you start ignoring them, which defeats
the point. Start a bit loose and tighten if you're missing real issues.

## Route alerts where you'll see them

- **Use a dedicated `#alerts` channel** so they're not buried in chat.
- **Ping a role** (e.g. `@Admin`) for urgent ones like downtime, so someone actually
  sees it.
- **Keep noisy, low-priority alerts** out of channels that ping people.

## Act on an alert

When you get one:

- **Down:** try a restart from Discord or the panel (see *Controlling your server
  from Discord*); if it won't come back, see *Server won't start*.
- **High memory:** schedule/trigger a restart; review mods (see *Reducing lag and
  monitoring resources*).
- **Crash loop:** break the loop and read the error (see *Recovering from a crash
  loop*).

## Troubleshooting

- **Not getting alerts:** confirm the bot is online, the server is linked, and the
  alert channel is set (see *Troubleshooting the bot*).
- **Too many alerts:** raise the thresholds and turn off low-value ones.
- **Missed a downtime alert:** make sure downtime alerts are enabled and ping a role,
  and that the bot itself was online at the time.
