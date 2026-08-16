---
title: Your game server won't start
slug: server-wont-start
description: A step-by-step checklist for a server that crashes on boot or won't stay online.
---

A server that won't start almost always tells you why — in the console. Work
through these in order and you'll find it.

## 1. Read the console

Open the **Console** tab and press **Start**. Watch what prints, then scroll to the
first **ERROR** or the last lines before it stopped. The cause is nearly always
there. Copy those lines somewhere; you'll want them if you need us.

## 2. Check the usual causes

**Version or loader mismatch (most common).** If you changed the Minecraft
version, server type, or installed a modpack, the startup jar and the world/mods
must all match. A Forge world won't load on Fabric; a 1.20 mod crashes a 1.21
server. Set the version/loader to match your content and restart.

**EULA not accepted.** A fresh server stops with a note about `eula.txt`. Accept
the EULA (the panel prompts you, or set `eula=true` in `eula.txt`) and start again.

**A bad config edit.** If it broke right after you edited `server.properties` or a
plugin config, a malformed line is the likely cause. Revert your change — the
console usually names the file and line.

**A broken plugin or mod.** The error names a file (`at com.someplugin…`). Remove
that one `.jar` from `plugins/` or `mods/`, restart, and see if it boots. Add
things back one at a time.

**Out of memory.** If you see `OutOfMemoryError` or the server dies while loading a
big world/pack, it wants more RAM than your plan provides. Lower the load (smaller
pack, fewer mods) or upgrade the plan.

**Corrupt world.** Errors mentioning `level.dat`, `region`, or `chunk` point at
world corruption. Restore your most recent backup (see *Managing worlds and
backups*).

## 3. Try a clean boot

To prove whether it's your content or the base server:

1. Stop the server.
2. Temporarily move `plugins/` (or `mods/`) contents aside.
3. Start. If it boots clean, a plugin/mod was the cause — add them back one by one.

## 4. Still stuck?

Open a support ticket with:

- your server address,
- what you changed just before it broke, and
- the **last 20–30 console lines** (or a copy of `logs/latest.log`).

That's almost always enough for us to pinpoint it quickly. Please don't keep
hammering **Start** in a loop — it won't fix a config/version problem and it makes
the log harder to read.
