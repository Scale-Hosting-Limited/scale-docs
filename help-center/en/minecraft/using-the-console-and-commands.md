---
title: Using the console and common commands
slug: using-the-console-and-commands
description: Run server commands from the panel console and read the log when something goes wrong.
---

The **console** in the panel is a direct line to your server. Anything you'd type
in-game as an operator, you can type here — without the leading slash — plus it's
where the server prints what it's doing.

## Running commands

Open your server's **Console** tab. Type a command and press Enter. From the
console you don't use a leading `/`:

```
say Server restarting in 5 minutes
op PlayerName
whitelist add PlayerName
time set day
weather clear
```

Output and errors appear in the same window. This is the first place to look when
anything misbehaves.

## Handy commands

**Players & admin**
- `list` — who's online
- `op` / `deop` `<name>` — grant/remove admin
- `kick` / `ban` / `pardon` `<name>` — moderation
- `whitelist add/remove/list <name>`

**World & time**
- `time set day|night`
- `weather clear|rain|thunder`
- `gamerule keepInventory true`
- `difficulty easy|normal|hard`
- `save-all` — force-save the world (do this before manual backups)

**Teleport & give (ops)**
- `tp <player> <x> <y> <z>`
- `give <player> <item> <count>`
- `gamemode creative|survival <player>`

## Reading the log

The console doubles as your log. A few things to know:

- **`Done (12.345s)! For help, type "help"`** — the server finished starting and is
  accepting players.
- **`[Server thread/INFO]`** — normal information.
- **`[Server thread/WARN]`** — a warning; usually fine, worth reading.
- **`[Server thread/ERROR]`** and stack traces (lines starting with `at ...`) —
  something failed. The first few lines of an error usually name the plugin or
  cause.

When you ask us for help, copy the **last 20–30 lines** around an error — that's
almost always enough to diagnose it. You can also download the full log from the
File Manager under `logs/latest.log`.

## Restarting vs stopping

- **Restart** applies most config and plugin changes. Use the panel's Restart
  button, or `stop` in the console (the panel brings it back up).
- Some changes (server version, startup flags) need a **full stop and start**, not
  just a reload.

## A safety note

The console has full control of the server. Be careful pasting commands you don't
recognise from the internet, and never run `op` for someone you don't trust — an
operator can do anything you can.
