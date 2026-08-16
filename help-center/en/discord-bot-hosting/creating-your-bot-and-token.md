---
title: Creating your bot and token
slug: creating-your-bot-and-token
description: Set up a bot application in the Discord Developer Portal and get its token.
---

Before hosting, your bot needs an **application** and a **token** from Discord.
The token is the bot's password — treat it like one.

## Create the application

1. Go to the **Discord Developer Portal** (discord.com/developers) and sign in.
2. **New Application**, give it a name, and create it.
3. Open the **Bot** tab → **Add Bot**.

## Get the token

On the **Bot** tab, click **Reset Token** and copy it. **This is shown once** —
copy it somewhere safe immediately. You'll add it to your hosting as an
environment variable (see *Environment variables and secrets*); never paste it
into your code where it could end up in Git.

If you ever expose a token, **reset it** in this same place — the old one stops
working instantly.

## Enable the right intents

Under the **Bot** tab, enable the **Privileged Gateway Intents** your bot uses:

- **Message Content Intent** — required if your bot reads message text (prefix
  commands). Not needed for pure slash-command bots.
- **Server Members Intent** — if your bot needs member lists / join events.
- **Presence Intent** — if it reads presence/status.

Enable only what you use. Your code must request the matching intents too, or the
bot connects but doesn't receive those events.

## Invite the bot to your server

1. Open **OAuth2 → URL Generator**.
2. Tick **bot** (and **applications.commands** for slash commands).
3. Tick the **permissions** your bot needs (start minimal — Send Messages, and
   whatever it actually does).
4. Copy the generated URL, open it, and add the bot to your server.

## Next

With the application created, the intents enabled, and the token copied, you're
ready to deploy: *Uploading your bot code*, then *Environment variables and
secrets* to store the token.

## Common mistakes

- **Bot online but ignores messages:** missing Message Content Intent (or slash
  commands not registered).
- **"Invalid token":** it was mistyped, or reset after you copied it — reset again
  and update your env variable.
- **Bot has no permissions in a channel:** re-invite with the right permissions or
  fix the channel overrides.
