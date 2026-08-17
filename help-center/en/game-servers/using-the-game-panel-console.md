---
title: Using the game panel console
slug: using-the-game-panel-console
description: Read live server output and run commands from the panel console.
---

The console is the beating heart of your game panel. It shows what the server is
doing in real time and lets you type commands straight to it. Learning to read it is
the fastest way to solve most problems yourself.

## What the console shows

When the server runs, it prints a live log: startup steps, players joining and
leaving, warnings, and errors. Watching it during startup tells you immediately
whether the server came online cleanly or hit a problem.

The console only shows output **while the server is running or starting**. If it's
blank, the server is probably stopped — hit **Start**.

## Running commands

Type a command in the box at the bottom and press Enter. It's sent to the server
exactly as if you typed it in-game as an admin — but from the panel you don't need
to be online or opped.

Examples vary by game, but common ones include:

- Broadcasting a message to players
- Saving the world
- Kicking or banning a player
- Changing settings that support live commands

Check your game's own guide (or *Bot commands reference* if you drive it from
Discord) for the exact syntax.

## Reading errors

When something breaks, the console is where it says so. Look for:

- **`ERROR` / `SEVERE` / `FATAL`** lines — the actual problem.
- **Stack traces** (indented blocks) — the first few lines usually name the culprit,
  often a specific mod or plugin.
- **Port or bind errors** — something's already using the port, or the server didn't
  shut down cleanly.
- **Out-of-memory** messages — the server needs more RAM or is overloaded (see
  *Out of memory and resource limits*).

Copy the relevant lines when you open a ticket — they tell us far more than "it
won't start."

## Console tips

- **Scroll up** to see what happened before an error — the cause is usually just
  above the crash.
- **Restart to reproduce** — if you're chasing a startup error, restart and watch
  from the top.
- **Don't spam commands** while it's starting; wait until it reports it's ready.

## When the console won't help

Some errors are written to **log files** rather than the live console — for deeper
digging, see *Reading server logs*. And if the server crashes instantly on start,
the console may scroll past the error; check the log files for the full record.

For step-by-step fixes see *Server won't start* and *Recovering from a crash loop*.
