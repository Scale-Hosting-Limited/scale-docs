---
title: server.properties explained
slug: server-properties-explained
description: What the common Minecraft server settings do and the ones you'll actually change.
---

`server.properties` is the main configuration file for a Java Minecraft server.
You can edit it in the panel's **File Manager**, or many settings have a toggle on
the **Startup**/**Settings** tab. Change a value, save, and **restart** for it to
take effect.

## The settings you'll actually change

**`gamemode`** — default mode for new players: `survival`, `creative`,
`adventure`, or `spectator`.

**`difficulty`** — `peaceful`, `easy`, `normal`, or `hard`. Peaceful disables
hostile mobs.

**`max-players`** — how many can be online at once. Higher counts need more RAM;
don't set this above what your plan can handle.

**`motd`** — the "message of the day" shown in the server list. Supports colour
codes.

**`level-name`** — the world folder to load (default `world`). Change this to
swap between worlds (see *Managing worlds and backups*).

**`level-seed`** — the seed used when a new world is generated. Only matters
before the world exists.

**`pvp`** — `true`/`false` to allow players to damage each other.

**`online-mode`** — leave this **`true`**. It verifies players against Mojang's
auth servers. Setting it `false` ("offline mode") lets anyone join under any name
and is a security and piracy risk; our terms require it stays on.

**`white-list`** — `true` to restrict joining to approved names. Manage names with
`whitelist add/remove` (see *Operators, whitelist and permissions*).

**`view-distance`** and **`simulation-distance`** — how many chunks are sent and
ticked around each player. These are the biggest performance levers: lowering them
(e.g. view 8, simulation 6) dramatically reduces lag on busy servers.

**`spawn-protection`** — radius around spawn that non-ops can't build in. Set to
`0` to disable.

**`enable-command-block`** — `true` if your builds use command blocks.

## Settings to leave alone unless you know why

- **`server-port`** — managed by us; changing it can break connectivity.
- **`server-ip`** — leave blank; it's set for you.
- **`online-mode`** — as above, keep it `true`.

## Editing safely

1. Stop the server (some values only load at boot).
2. Edit `server.properties` in the File Manager.
3. Save, then start the server.
4. If something breaks, the values are plain text — set it back and restart. Keep a
   backup of the file before big changes.

A malformed line (for example a `true`/`false` field set to something else) can
stop the server booting. If the server won't start after an edit, that's the first
place to check — see *Server won't start*.
