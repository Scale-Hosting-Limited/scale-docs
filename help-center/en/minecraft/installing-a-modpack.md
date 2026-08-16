---
title: Installing a modpack
slug: installing-a-modpack
description: Install a CurseForge or Modrinth modpack on your server and connect with the matching client.
---

A modpack is a curated bundle of mods, configs, and sometimes a custom world.
Installing one server-side is straightforward, but the golden rule is: **the
server and every player must run the same pack at the same version.**

## Before you start

- Decide on the pack and note its **exact version** and its **Minecraft version**
  and **mod loader** (Forge, Fabric, NeoForge, or Quilt).
- Back up your current world if you want to keep it — installing a pack usually
  replaces the server files. See *Managing worlds and backups*.

## Option 1: install from the panel

Many popular packs can be installed directly:

1. Open your server and go to the **Modpacks** (or **Content**) tab.
2. Search for the pack, choose the version that matches the pack's release, and
   start the install.
3. Wait for it to finish — a large pack is hundreds of files, so give it a few
   minutes. The panel shows progress.
4. Set the server to the matching loader/version if prompted, then **Start**.

## Option 2: install a specific pack manually

If a pack isn't in the browser, or you want a precise build:

1. Download the **server files** for the pack (most packs publish a separate
   "server pack" — do not upload the client zip).
2. Stop the server.
3. In the **File Manager**, upload the server pack `.zip` to the main directory
   and extract it. If it created a subfolder, move the contents up so the
   `mods/` folder and the start jar sit in the root.
4. Set the correct **startup jar / loader version** in the server settings.
5. Start the server and watch the console until it shows `Done`.

## Connect with the right client

Players install the **same pack** in their launcher (CurseForge, Modrinth,
Prism, ATLauncher, etc.), launch it, and add your server address as usual. A
vanilla client cannot join a modded server, and a mismatched pack version will be
rejected.

## Performance

Modpacks are heavier than vanilla — big packs can want 6–10 GB of RAM. If the
server lags, crashes on start with an out-of-memory error, or takes a long time to
load, you may need a larger plan. See *Improving performance and reducing lag*.

## Troubleshooting

- **Crashes on start:** almost always a loader/version mismatch or a corrupt
  download. Confirm the loader and Minecraft version match the pack, and reinstall
  if a file may have been truncated.
- **Missing mods for players:** they're on a different pack version — have everyone
  update to the exact same build.
- **World didn't carry over:** modpacks often reset the world; restore your backup
  into the pack's world folder after install.

If a pack won't boot after you've checked the versions, open a ticket with the
pack name, version, and the last 30 lines of the console.
