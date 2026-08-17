---
title: Installing mods and workshop content
slug: installing-mods-and-workshop-content
description: Add mods, plugins, and Steam Workshop content to your game server safely.
---

Mods and workshop content are what make a game server yours. The exact method
depends on the game, but the principles — back up first, match versions, add
gradually — apply everywhere. (For Minecraft specifically, see that section's
guides.)

## Before you install anything

1. **Take a backup** (see *Backing up and restoring*). Mods are the most common
   cause of a broken server; a backup makes it reversible.
2. **Check compatibility** — the mod must match your game **version** and, for
   modded frameworks, the right loader.
3. **Note dependencies** — many mods need other mods to run. Install those too.

## Common install methods

Different games do this differently:

- **Steam Workshop (ARK, Rust, Garry's Mod, etc.):** add Workshop item IDs in the
  server's **Startup** settings or a mods list. The server downloads them on start.
- **Drop-in plugin/mod folders:** upload files into a `mods`, `plugins`, or
  `oxide/plugins` folder via **Files** or **SFTP** (see *Connecting with SFTP*).
- **Config-driven:** some games list mods in a config file you edit directly.

Your game's guide will name the exact folder or setting — check it before uploading.

## Install one at a time

When adding several mods, **add them a few at a time and restart** between batches.
If the server breaks, you know which mod did it. Installing twenty at once and then
debugging a crash is far harder.

## Match versions carefully

The biggest source of mod problems is a **version mismatch** — a mod built for an
older or newer game version. After a game update, expect to update your mods too, or
they may stop the server booting.

## Steam Workshop collections

For Workshop-based games you can often point the server at a **collection ID** so it
loads a whole curated set. Handy, but the same rule applies: everything in the
collection must match your game version.

## Removing a mod

1. Stop the server.
2. Remove the mod's files (or its Workshop ID from the startup list) **and** any
   config it created.
3. Restart and watch the console.

Leaving orphaned config behind is a common cause of errors after removing a mod.

## Troubleshooting

- **Server won't start after a mod:** remove the last mod you added, restart, and
  reintroduce mods one by one. See *Server won't start*.
- **Missing dependency errors:** the console names what's missing — install it.
- **Workshop items not downloading:** check the IDs are correct and the server has
  finished downloading before you join.
- **Everything's broken:** restore the backup you took first, then try again more
  slowly.
