---
title: Getting started with Discord bot hosting
slug: getting-started-with-discord-bot-hosting
description: Host your Discord bot online 24/7 — how it works and what you'll need.
---

Discord bot hosting keeps your bot running around the clock on our servers, so it
stays online even when your computer is off. If you've written a bot (or are about
to), this is where it lives in production.

## What you'll need

- **Your bot's code** — a project in Node.js (discord.js), Python (discord.py /
  Pycord / nextcord), Java (JDA), Go, or another supported runtime.
- **A bot application and token** from the Discord Developer Portal — see *Creating
  your bot and token*.
- A **Discord bot hosting plan** with us.

## How it works

Your plan gives you a server instance with a **console**, a **file manager**, and
**SFTP** access — the same panel you'd use for a game server. You:

1. **Upload your code** (file manager, SFTP, or a Git pull).
2. **Install dependencies** (npm/pip/etc.).
3. **Set the startup command** so the panel knows how to run your bot.
4. **Add your token and any secrets** as environment variables.
5. **Start it** — the bot connects to Discord and comes online.

The panel keeps it running and restarts it if it crashes, so it stays online
without you babysitting it.

## Choosing a plan

Most small-to-medium bots run comfortably on an entry plan. Size up if your bot:

- serves many servers or heavy traffic,
- does heavy processing (audio/music, image generation, large data),
- or needs more memory for a big cache.

You can upgrade later, so start where you are and scale when needed.

## Which language/runtime?

We support the popular bot stacks — Node.js and Python are the most common. Pick
the one your bot is written in; the setup steps are the same shape, differing only
in the run command and how dependencies install. See *Supported languages and
runtimes* and *Setting the startup command*.

## Next steps

1. *Creating your bot and token* — set up the application in Discord.
2. *Uploading your bot code* — get your project onto the server.
3. *Setting the startup command* and *Installing dependencies*.
4. *Environment variables and secrets* — store your token safely.
5. *Keeping your bot online* — restarts and uptime.

If you get stuck at any step, open a support ticket with your runtime and the
console output.
