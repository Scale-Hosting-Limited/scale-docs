---
title: Configuring status notifications
slug: configuring-status-notifications
description: Have the bot post to a channel when your server goes up, down, or fills up.
---

The bot can keep your community informed automatically — posting to a channel when
the server's status changes so nobody has to keep asking "is it up?"

## Choose a channel

1. In your server's **Discord** tab (or with `/settings`), pick the channel the bot
   should post in.
2. Make sure the bot can **read and send messages** (and embed links) in that
   channel — see *Setting up permissions and roles*.

## What it can notify

Depending on the abilities enabled for the link:

- **Online / offline** — a message when the server starts or stops.
- **Crash / recovery** — if the server goes down unexpectedly and when it's back.
- **Player milestones** — optional posts when the server fills up or empties.
- **A live status message** — a single embed the bot keeps updated with the current
  status and player count, instead of a stream of messages.

## Mentions

You can have important notifications (like the server going down) **ping a role** so
staff are alerted. Set the role in the bot settings; use it sparingly so people
don't mute the channel.

## Keeping it tidy

- Give the bot its own **#server-status** channel so notifications don't bury
  conversation.
- Prefer the **single live status embed** over per-event messages if you find the
  channel noisy.
- Turn off notification types you don't care about in `/settings`.

## Troubleshooting

- **No posts appearing:** the bot can't send in that channel (permissions), the
  wrong channel is selected, or the ability is disabled. See *Troubleshooting the
  bot*.
- **Duplicate posts:** you may have linked the same server twice — check for a
  stale link and `/unlink` the extra one.
- **Pings not working:** the role isn't set, or the bot lacks permission to mention
  it.
