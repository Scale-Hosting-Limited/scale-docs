---
title: Troubleshooting your bot
slug: troubleshooting-your-bot
description: Fixes for the most common Discord bot hosting problems.
---

Almost every bot problem shows up in the **console**. Start it, watch the output,
and match what you see below.

## Bot won't start / exits immediately

- **"Cannot find module" / `ModuleNotFoundError`:** dependencies aren't installed —
  run `npm install` / `pip install -r requirements.txt` and restart (see
  *Installing dependencies*).
- **"Cannot find file" / wrong entry point:** the startup command points at the
  wrong file, or files are in a subfolder — fix the path or move files to the root
  (see *Setting the startup command*).
- **Syntax error:** the stack trace names the file and line — fix and restart.
- **`node`/`python` not found:** wrong runtime image/version selected, or use
  `python3`.

## Bot starts but shows offline in Discord

- **"Invalid token" / login fails:** the `DISCORD_TOKEN` variable is missing,
  mistyped, or was reset after you copied it. Reset the token and update the
  variable (see *Environment variables and secrets*).
- No "logged in" line in the console at all — it's not reaching Discord; check the
  token and your network calls.

## Bot online but ignores messages / commands

- **Prefix commands do nothing:** you're missing the **Message Content Intent** —
  enable it in the Developer Portal *and* request it in your code (see *Creating
  your bot and token*).
- **Slash commands don't appear:** they weren't registered, or **global** commands
  are still propagating (up to an hour) — test with guild commands.
- **Missing permissions in a channel:** re-invite with the right permissions or fix
  channel overrides.

## Bot keeps restarting (crash loop)

The panel restarts a crashed bot, so a bug on startup looks like a loop. It's not
fixed by restarting — read the first error in the console and address it (bad
token, missing dep, unhandled exception on boot).

## Data resets when it restarts

You're keeping state in memory. Persist it to storage that survives restarts — see
*Using a database with your bot*.

## Running out of memory

An ever-growing cache is the usual cause. Cap your caches; if the bot genuinely
needs more, upgrade the plan.

## Still stuck?

Open a support ticket with:

- your **runtime** (Node/Python/…) and version,
- the **startup command**, and
- the **console output** around the error (last 20–30 lines; redact secrets).

We can't debug your bot's logic for you, but we'll help you read the error and rule
out the platform.
