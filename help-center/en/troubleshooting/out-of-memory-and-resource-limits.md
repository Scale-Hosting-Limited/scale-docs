---
title: Out of memory and resource limits
slug: out-of-memory-and-resource-limits
description: Fix out-of-memory crashes and understand your plan's resource limits.
---

"Out of memory" errors and sudden crashes under load almost always mean your service
has hit a resource limit. This explains what the limits are, how to spot when you're
hitting them, and what to do about it.

## Your plan's limits

Every plan comes with set amounts of:

- **RAM (memory)** — the big one for game servers and apps.
- **CPU** — processing power, measured in cores/percentage.
- **Disk** — storage for your files, world, database, and backups.

Your service can't exceed these. When it tries, you get lag, errors, or a crash —
depending on which limit you hit.

## Spotting an out-of-memory problem

Signs you're running out of RAM:

- Console errors mentioning **`OutOfMemoryError`**, `memory`, or `heap`.
- The server **crashes under load** — fine when quiet, dies when busy.
- Steadily **rising memory** in the graphs until it hits the ceiling, then a crash.

Watch the memory graph **while it's busy** — that's when the ceiling gets hit.

## Fixing memory issues

1. **Restart regularly.** Memory creeps up over days; a daily scheduled restart
   clears it (see *Scheduling restarts and tasks*).
2. **Reduce what's loaded.** Fewer/lighter mods and plugins, smaller view/simulation
   distance, fewer loaded chunks or entities (see *Reducing lag and monitoring
   resources*).
3. **Check your allocation.** Some games let you set how much RAM the server process
   uses — make sure it's set to use the plan's memory, not less, and not
   over-committed.
4. **Find a leak.** If memory climbs relentlessly even when quiet, a specific
   mod/plugin may be leaking — remove suspects one at a time (see *Installing mods
   and workshop content*).

If it still runs out after all that, you genuinely need more RAM.

## Disk full

A full disk causes its own failures — saves fail, backups won't run, databases error.

- **Delete old backups** you don't need (or download and remove them — see *Backing
  up and restoring*).
- **Clear old logs** and temporary files.
- **Remove unused mods, worlds, or files.**
- Still full? You've outgrown the disk — upgrade.

## CPU maxed

If CPU is pinned at 100%, the server can't keep up — you'll see stutter and slow
ticks. Reduce load (mods, distance, entities) or upgrade CPU. One maxed core can
bottleneck an entire server.

## When to upgrade

If a resource is pinned at the limit even after tuning, upgrading is the honest fix —
no configuration makes hardware do more than it can. See *Upgrading or downgrading a
service*, or open a ticket for advice on the right size (see *Choosing the right
plan*).

## Still crashing?

Open a ticket with the **exact error** and a note of **which resource** the graphs
show maxing out. That tells us immediately whether it's a tuning fix or a sizing
one.
