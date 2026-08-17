---
title: Reducing lag and monitoring resources
slug: reducing-lag-and-monitoring-resources
description: Read your CPU, RAM, and disk usage and fix a laggy game server.
---

Lag almost always comes down to resources — the server needs more CPU, RAM, or disk
than it has, or something is wasting them. The panel shows you exactly what's being
used, so you can find the cause instead of guessing.

## Read your resource graphs

In the game panel you'll see live usage for:

- **CPU** — how hard the processor is working. Sustained high CPU (near your limit)
  causes stutter and slow ticks.
- **Memory (RAM)** — how much is in use. Hitting the ceiling causes lag, crashes, or
  out-of-memory errors (see *Out of memory and resource limits*).
- **Disk** — storage used. A full disk stops backups, saves, and sometimes the whole
  server.

Watch these **while players are on** — that's when problems show. Idle usage tells
you little.

## Common causes of lag

- **Too many players/mods for the plan** — the most common cause. Bigger worlds and
  more players need more resources.
- **A heavy mod or plugin** — one badly optimised addon can drag everything down.
- **View/render or simulation distance too high** — generous distances multiply the
  work the server does per player.
- **Runaway entities** — huge mob farms, dropped items, or spawned creatures pile up
  and hammer the CPU.
- **No regular restart** — memory creeps up over days; a daily restart helps (see
  *Scheduling restarts and tasks*).

## Fixes that usually help

1. **Restart daily** on a schedule — clears memory, resets slowdowns.
2. **Trim simulation/view distance** a notch — often a big win for little downside.
3. **Audit mods/plugins** — remove or replace anything heavy; add them back one at a
   time to spot the culprit (see *Installing mods and workshop content*).
4. **Clear built-up entities** — many games have a command or plugin to clear dropped
   items and cap mob farms.
5. **Keep disk usage down** — delete old backups and logs.

## When you've outgrown the plan

If usage is pinned at the limit even after tuning, you've simply outgrown the plan.
Upgrading to more RAM/CPU is the honest fix — no amount of config makes a server do
more than its hardware allows. See *Choosing the right plan*, or open a ticket for
advice on sizing.

## Monitor over time

- Check the graphs after adding mods or when player numbers grow.
- If you drive the server from Discord, our bot can surface live stats and alerts
  (see *Viewing stats and console in Discord* and *Alert thresholds and
  notifications*).

## Troubleshooting

- **CPU pinned at 100%:** reduce distance/mods, or upgrade CPU; one core maxed can
  bottleneck a whole server.
- **RAM always full:** raise the allocation if your game lets you, or upgrade; see
  *Out of memory and resource limits*.
- **Lag only at peak times:** it's a capacity issue — plan for your busiest hour, not
  your quietest.
