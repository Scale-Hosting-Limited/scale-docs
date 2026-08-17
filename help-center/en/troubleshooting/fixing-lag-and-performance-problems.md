---
title: Fixing lag and performance problems
slug: fixing-lag-and-performance-problems
description: Track down what's slowing your server or site and fix it.
---

Lag is frustrating but rarely mysterious — it almost always traces to a resource
running out or something wasting it. This is a general checklist for diagnosing and
fixing slowness across game servers, websites, and apps.

## First, find the bottleneck

Open your panel's **resource graphs** and watch them **under load** (while it's
actually being used):

- **CPU pinned near the limit** → the processor can't keep up. Reduce work or
  upgrade CPU.
- **RAM near full** → not enough memory; leads to lag and crashes (see *Out of memory
  and resource limits*).
- **Disk full or slow** → saves, backups, and databases suffer.

Whichever is maxed out is your bottleneck. Fix that one first.

## Game servers

- **Restart daily** — memory creeps up over time; a scheduled restart resets it (see
  *Scheduling restarts and tasks*).
- **Lower view/simulation distance** a notch — often a big gain.
- **Audit mods/plugins** — one heavy addon can drag everything; remove and re-add one
  at a time (see *Installing mods and workshop content*).
- **Clear built-up entities** — item drops and mob farms hammer the CPU.

For the full game-server treatment, see *Reducing lag and monitoring resources* and,
for Minecraft, *Improving performance and reducing lag*.

## Websites

- **Enable caching** — a caching plugin or layer cuts repeated work dramatically
  (huge for WordPress).
- **Optimise images** — oversized images are the most common cause of a slow page.
- **Check your database** — slow queries and a bloated database drag the whole site;
  clean up and optimise tables (see *Managing MySQL databases*).
- **Update everything** — old themes, plugins, and PHP versions are slower and less
  secure (see *Choosing a PHP version*).
- **Remove unused plugins/extensions** — each one adds load.

## Rule out the network

Sometimes "lag" is the connection, not the server:

- **Test from another device/network** — if it's fast elsewhere, the issue is your
  local connection.
- **Check your ping** to the server. High latency to a distant location is physics,
  not a fault — a closer server location helps.
- See *Can't connect to your server* for connection-side checks.

## When you've genuinely outgrown the plan

If resources are pinned even after tuning, the honest answer is you need more. No
configuration makes hardware do more than it can. Upgrading CPU/RAM is the fix — see
*Upgrading or downgrading a service*, or ask us for sizing advice.

## Still stuck?

Open a ticket with:

- **Which resource** is maxing out (from the graphs).
- **When** it happens (peak times? always?).
- **What you've tried** already.

That lets us pinpoint it fast instead of guessing (see *Opening a support ticket*).
