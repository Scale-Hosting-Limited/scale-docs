---
title: Keeping your bot online 24/7
slug: keeping-your-bot-online
description: How the panel keeps your bot running, and how to make your bot restart-safe.
---

The whole point of hosting is that your bot stays online without your computer.
Here's how that works and how to make your bot resilient.

## Automatic restarts

The panel keeps your bot's process running. If it crashes or exits, the panel
brings it back up — so a transient error doesn't take your bot offline for good.
You don't need a separate process manager like PM2; the panel is that layer.

## Write restart-safe code

Because the process can restart, design your bot to come back cleanly:

- **Don't rely on in-memory state surviving a restart.** If you cache things in
  memory, be ready to rebuild them on startup, or persist them (see *Using a
  database with your bot*).
- **Reconnect gracefully** — discord.js and discord.py handle gateway reconnects
  for you; don't fight them with your own reconnection loop.
- **Handle errors** rather than letting one unhandled rejection crash the whole
  bot. Log it and carry on where it's safe to.

## Avoid crash loops

If your bot crashes immediately on every start, the panel will keep restarting it —
a "crash loop." That's usually a bug (bad token, missing dependency, syntax error),
not something restarts fix. Watch the console after a start; if it dies right away,
see *Troubleshooting your bot* rather than leaving it looping.

## Keep it within resources

A bot that leaks memory will eventually be restarted when it hits its limit. That's
a safety net, not a fix — track down leaks (unbounded caches are the usual
culprit). If your bot legitimately needs more memory (big cache, music, heavy
libraries), size up your plan.

## Scheduled restarts (optional)

Some people schedule a nightly restart to clear memory and pick up updates. If your
service offers a scheduler, a daily restart at a quiet hour is a reasonable habit —
just make sure your bot handles restarts cleanly first.

## Uptime expectations

Your bot stays up as long as the service is active and paid, the code doesn't crash
loop, and it's within resources. Planned maintenance is rare and communicated. If
your bot shows offline in Discord but the console says it's running, check the
token and intents (see *Creating your bot and token*).
