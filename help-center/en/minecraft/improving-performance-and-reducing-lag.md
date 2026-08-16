---
title: Improving performance and reducing lag
slug: improving-performance-and-reducing-lag
description: Diagnose whether lag is TPS or ping, and the settings and plugins that fix it.
---

"Lag" is really two different problems, and the fix depends on which one you have.
Figure out which first.

## TPS vs ping

- **Low TPS (server-side lag):** the world itself runs slow — mobs stutter, blocks
  break with a delay, everyone is affected equally. Check with `/tps` (Paper) —
  20 is perfect, below ~18 is noticeable. This is about server load.
- **High ping (client-side lag):** only some players rubber-band while others are
  fine. That's network distance/quality between that player and the server, not
  the server being overloaded.

Run `/tps` (or a plugin like Spark) before changing anything — it tells you which
battle you're fighting.

## Fixing low TPS

**1. Use a performance-oriented server type.** Paper (or Purpur) is far faster
than Vanilla/Spigot and safe for most servers. Switch in the panel and restart.

**2. Lower distances.** In `server.properties`, `view-distance` and
`simulation-distance` are the biggest levers. Try `view-distance=8` and
`simulation-distance=6`; drop simulation to 4 on busy servers.

**3. Tune Paper's configs.** In `config/paper-world-defaults.yml` you can reduce
mob spawn caps, entity ranges, and hopper frequency. Sensible mob limits alone
often recover several TPS.

**4. Find the culprit with Spark.** Install the Spark plugin and run
`/spark profiler` — it points to the exact plugin, entity, or chunk eating the
tick. Common offenders: too many entities (mob farms, item drops), a heavy plugin,
or redstone/hopper contraptions.

**5. Cut entities.** Use `/kill @e[type=item]` to clear dropped items, cap mob
farms, and consider a plugin like ClearLagg with conservative settings.

**6. Give it more RAM — but only if RAM is the issue.** If the console shows the
server pausing for garbage collection or hitting out-of-memory, a larger plan
helps. RAM does **not** fix TPS caused by bad plugins or too many entities — more
memory won't make a slow tick faster.

## Fixing high ping

- Ping is largely down to physical distance to the server location. Choose the
  region closest to most of your players when ordering.
- A player on Wi-Fi or a poor connection will ping high regardless — wired
  connections help.
- If everyone from one region lags but the server's TPS is a healthy 20, the
  server is fine; it's a network path issue, not something a bigger plan fixes.

## Modpacks

Modded servers are heavier by nature. Big packs legitimately want 6–10 GB of RAM
and more CPU. If a pack is unplayable on your current plan after tuning, size up.

## When to ask us

If TPS is low and Spark points at something you can't identify, open a ticket with
the Spark report link and your plugin list — we can help read it.
