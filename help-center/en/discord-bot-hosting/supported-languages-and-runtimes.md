---
title: Supported languages and runtimes
slug: supported-languages-and-runtimes
description: Which languages you can host a Discord bot in, and how each is set up.
---

You can host a bot written in any of the common Discord bot stacks. The setup is
the same shape for all of them — upload code, install dependencies, set a run
command — differing only in the tooling.

## Node.js (discord.js)

The most popular choice.

- **Library:** discord.js (or Eris, Oceanic).
- **Install:** `npm install`
- **Run:** `node index.js` (or `npm start`).
- **Versions:** pick a modern Node (18/20/22) on the Startup tab; discord.js v14
  needs Node 16.11+.
- **TypeScript:** build (`npm run build`) then run the compiled `dist/`.

## Python (discord.py / Pycord / nextcord)

- **Library:** discord.py, Pycord, nextcord, or hikari.
- **Install:** `pip install -r requirements.txt`
- **Run:** `python main.py` (or `python3`).
- **Versions:** choose a recent Python (3.11/3.12).

## Java (JDA)

- **Library:** JDA or Discord4J.
- **Build:** produce a jar (Maven/Gradle), locally or with a build step.
- **Run:** `java -jar yourbot.jar`.

## Go, Rust, and others

- **Go:** DiscordGo — build the binary and run it.
- **Rust:** Serenity/Twilight — build in release mode and run the binary.
- Any runtime that can hold a websocket to Discord and that we provide an image for
  will work; if you're unsure whether yours is supported, ask us.

## Choosing

Use whatever your bot is already written in — there's no advantage to rewriting.
For a brand-new bot, **Node.js (discord.js)** and **Python (discord.py)** have the
largest communities and the most tutorials, which makes getting unstuck easier.

## Common setup notes

- Match the **runtime version** on the Startup tab to what your library needs.
- Keep dependencies in the standard manifest (`package.json` / `requirements.txt`)
  so they install cleanly on the server.
- Store your token and secrets as environment variables regardless of language (see
  *Environment variables and secrets*).

If your language needs a specific image or version we don't list, open a ticket —
we can usually help you get it running.
