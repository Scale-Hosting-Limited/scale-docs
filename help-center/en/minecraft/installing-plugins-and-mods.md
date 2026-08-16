---
title: Installing plugins and mods
slug: installing-plugins-and-mods
description: Add plugins (Paper/Spigot) or mods (Forge/Fabric) to your server safely.
---

How you add extra content depends on your server type.

## Plugins (Paper, Spigot, Purpur)

1. Download the plugin's `.jar` file from a trusted source (e.g. SpigotMC,
   Modrinth, Hangar).
2. In the panel's **File Manager**, open the `plugins/` folder and upload the
   `.jar` — or use the SFTP details on the panel to upload with a client like
   FileZilla.
3. **Restart** the server (a reload is not enough for most plugins).
4. Check the console for the plugin loading, and look for a new config folder
   under `plugins/`.

## Mods (Forge, Fabric)

1. Make sure your server type and version match the mod (a Fabric mod needs a
   Fabric server on the same Minecraft version).
2. Upload the mod `.jar` into the `mods/` folder.
3. Players must install the **same** client-side mods and the matching loader to
   join.
4. Restart the server.

## Keep it stable

- Add plugins/mods **one at a time** and restart, so if something breaks you know
  what caused it.
- Match versions carefully — most crashes on start are a version mismatch.
- Our anti-abuse scanning checks uploaded files; a jar flagged as malware will be
  removed and the upload stopped.
