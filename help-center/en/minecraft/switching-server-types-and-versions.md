---
title: Switching server types and versions
slug: switching-server-types-and-versions
description: Move between Vanilla, Paper, Forge, Fabric, and change your Minecraft version.
---

Minecraft servers come in different "types" — Vanilla, Paper, Forge, Fabric and more
— and each suits a different goal. This explains what they are, how to switch, and how
to change your Minecraft version without breaking your world.

## The main server types

- **Vanilla** — the pure, unmodified game. Simple, but no plugins or mods and heavier
  on resources.
- **Paper** (and Spigot/Bukkit) — the standard for **plugins**. Faster than Vanilla
  and hugely configurable. Best for survival, minigames, and most community servers.
- **Forge** — the standard for **mods** (large content mods, modpacks). Needs a
  matching modded client to join.
- **Fabric** — a lighter, modern **mod** loader, popular for performance mods and
  many modpacks. Also needs a matching client.

Rule of thumb: **plugins → Paper**, **mods/modpacks → Forge or Fabric**, **pure game
→ Vanilla**.

## Plugins vs mods (why the type matters)

- **Plugins** run **server-side only** — players join with a normal vanilla client.
  Paper/Spigot use these (see *Installing plugins and mods*).
- **Mods** change the game itself and usually require players to install the **same
  mods** and loader. Forge/Fabric use these.

Pick the type that matches what you want to run — you can't load Forge mods on Paper,
or Bukkit plugins on plain Forge.

## Switch your server type

1. **Back up first** — always (see *Managing worlds and backups*).
2. In the panel's **Startup/Settings**, change the **server type/jar** (e.g. from
   Vanilla to Paper) if your egg supports it, or select the matching option.
3. **Reinstall** if required so the new server files are put in place.
4. **Start** and watch the console (see *Using the console and commands*).

Your **world** usually carries over between Vanilla and Paper (they share the world
format), but moving **to or from heavily modded** setups can change or require a fresh
world — back up and expect to test.

## Change your Minecraft version

To run a newer (or older) Minecraft version:

1. **Back up your world** — a version change, especially an upgrade, can alter world
   data.
2. In **Startup**, set the **version** you want.
3. **Restart** (or reinstall if prompted).
4. **Update your plugins/mods** to match — this is essential; mismatched
   plugins/mods are the top cause of a server not starting after a version change (see
   *Installing plugins and mods*).

Players must use the **same Minecraft version** in their client to connect.

## Upgrading safely

- **Upgrades can be one-way** for your world — once opened in a newer version, a world
  may not open cleanly in the old one. Keep a pre-upgrade backup.
- **Wait for your plugins/mods to support** the new version before upgrading a live
  server — jumping early breaks things.
- **Test on a copy** if the server matters to your community.

## Troubleshooting

- **Won't start after switching:** a plugin/mod almost certainly doesn't match the new
  type/version — remove or update them one at a time (see *Server won't start*).
- **World missing or reset:** restore your backup; some type changes need a compatible
  world (see *Managing worlds and backups*).
- **Players can't join:** they must run the **same version** as the server.
- **Not sure which type you need:** plugins → Paper; mods/modpacks → Forge/Fabric; ask
  us if you're unsure (see *Opening a support ticket*).
