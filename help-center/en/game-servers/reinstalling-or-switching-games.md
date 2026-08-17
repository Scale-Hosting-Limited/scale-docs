---
title: Reinstalling or switching games
slug: reinstalling-or-switching-games
description: Reinstall a broken server or change which game it runs, safely.
---

Sometimes the cleanest fix is a fresh start — and sometimes you just want to run a
different game on the same server. Both are done from the panel, but they **erase or
replace files**, so read this before you click.

## Back up first — always

Reinstalling or switching games can **wipe your existing files**. Before you do
either:

1. Take a **backup** (see *Backing up and restoring*).
2. **Download** anything irreplaceable — worlds, configs, player data — to your own
   computer via SFTP (see *Connecting with SFTP*).

Treat a reinstall as destructive until proven otherwise.

## When to reinstall the same game

A reinstall gives you clean server files without changing the game. It's worth doing
when:

- The server is broken in a way you can't trace and a restore won't fix.
- Files are corrupted after a crash or bad update.
- You want a clean slate but keep the same plan and game.

Where possible, **your world/save data may be preserved** while the game files are
refreshed — but don't rely on it. Back up first.

## How to reinstall

1. **Stop** the server.
2. Go to **Settings → Reinstall** in the game panel.
3. Confirm. The panel re-runs the install and refreshes the server files.
4. When it finishes, **start** the server and watch the console (see *Using the game
   panel console*).

## Switching to a different game

You can change what a server runs by switching its **egg** (the install template) —
for example from one game to another on a compatible plan.

1. Back up and download anything you want to keep — switching games **replaces** the
   files.
2. In the panel, change the **egg/game** in the server settings (or open a ticket if
   the option isn't available to you).
3. Set the new game's **startup variables** (version, world name, etc.).
4. **Reinstall** so the new game's files are put in place.
5. Start and configure the new server from scratch.

## Changing version, not game

If you only want a **different version** of the same game (e.g. a newer build), you
usually don't need a full switch — change the **version** in **Startup** settings and
restart. Match your mods to the new version afterwards (see *Installing mods and
workshop content*).

## After a reinstall or switch

- Re-upload or reconfigure anything the fresh install doesn't include.
- Reinstall mods/plugins **one at a time** and confirm each works.
- Re-point any subdomain if the address changed (see *Setting up a subdomain*).

## Troubleshooting

- **Reinstall didn't fix it:** the problem may be in your world/config that carried
  over — restore an older, known-good backup instead.
- **Lost files after switching:** restore your backup or the copy you downloaded;
  this is why we say back up first.
- **New game won't start:** check the startup variables match the game version, and
  read the console error. See *Server won't start*.
