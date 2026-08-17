---
title: Recovering from a crash loop
slug: recovering-from-a-crash-loop
description: Stop a server that starts, crashes, and restarts over and over.
---

A crash loop is when your server starts, immediately crashes, restarts, and crashes
again — endlessly. It's alarming but very fixable. The trick is to break the loop,
read the error, and undo whatever change caused it.

## First: break the loop

While it's cycling, you can't read anything clearly. Stop it:

1. Hit **Stop** (or **Kill** if Stop won't take) in the panel.
2. If it keeps auto-restarting, turn off any **auto-restart/crash-detection** setting
   temporarily so it stays down while you investigate.

Now the server is stopped and you can work calmly.

## Read the crash error

The cause is in the logs, every time.

1. **Start it once** and watch the **console** from the top (see *Using the game
   panel console*).
2. Find the **first** `ERROR`/`FATAL` line before it dies — that's the cause, not the
   noise after it.
3. Check the **log files** too, since a fast crash can scroll the console (see
   *Reading server logs*).

## What usually causes it

- **A bad mod/plugin** — the most common cause, especially right after installing or
  updating one. The error usually names it.
- **A recent config change** — a typo or invalid value in a settings file.
- **A version mismatch** — mods that don't match the game version after an update.
- **Corrupted world/save data** — often after an unclean shutdown or full disk.
- **Out of memory** — it dies on startup for lack of RAM (see *Out of memory and
  resource limits*).

## Fix it by undoing the change

Ask: **what changed just before it started?**

- **Installed/updated a mod?** Remove it (and its config) and start again — add mods
  back one at a time (see *Installing mods and workshop content*).
- **Edited a config?** Revert your change, or restore the file from a backup.
- **Updated the game version?** Match your mods to it, or roll the version back.
- **Nothing obvious?** Restore your most recent **known-good backup** (see *Backing
  up and restoring*).

## If the world is corrupted

If the error points at the world/save data:

1. **Restore a backup** from before the corruption — the cleanest fix.
2. If you have no backup, some games have repair tools; as a last resort you may need
   to reset the affected part of the world.

This is exactly why regular backups matter — a corrupted world with a backup is a
five-minute restore.

## Turn auto-restart back on

Once it's running stably again, re-enable auto-restart/crash-detection so genuine,
one-off crashes recover on their own.

## Still looping?

Open a ticket with the **exact first error line** from the console and **what
changed** just before it started. That combination usually gets a fast answer (see
*Opening a support ticket*).
