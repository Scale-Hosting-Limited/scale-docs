---
title: Scheduling restarts and tasks
slug: scheduling-restarts-and-tasks
description: Automate restarts, backups, and commands so your server runs itself.
---

A well-run server does routine jobs on its own. The **Schedules** feature in your
game panel lets you set tasks to run automatically — a nightly restart, a periodic
backup, a scheduled announcement — so you're not doing it by hand.

## Why schedule a restart

Long-running game servers gradually use more memory and slow down. A **daily
restart** — ideally at a quiet time — clears that out and keeps performance steady.
It's the single most effective bit of automation you can set up.

## Create a schedule

1. In the game panel, open **Schedules** and create a new one.
2. Give it a **name** (e.g. "Nightly restart").
3. Set **when it runs** using the time fields (minute, hour, day). For a 5am daily
   restart, set hour `5`, minute `0`, and leave the day fields as "every day".
4. Save the schedule, then add **tasks** to it.

## Add tasks

A schedule runs one or more tasks in order. Common tasks:

- **Send command** — e.g. warn players ("Restarting in 5 minutes"), save the world,
  or run a game command.
- **Power action** — restart, start, or stop the server.
- **Create backup** — snapshot before the restart (see *Backing up and restoring*).

A polite restart schedule might be:

1. Send command: broadcast "Server restarting in 60 seconds".
2. (Add a delay if your panel supports it.)
3. Send command: save the world.
4. Power action: restart.

## Timing tips

- Pick a **low-traffic hour** for restarts so you disturb the fewest players.
- **Stagger** backups and restarts so they don't collide — back up *before* the
  restart, not at the same moment.
- **Don't over-restart.** Once a day is plenty for most servers; more often just
  interrupts players.

## Backups on a schedule

Automating backups means you always have a recent restore point. Set a daily backup
task and keep an eye on how many you retain (see *Backing up and restoring* for
limits and restores).

## Enable, disable, and test

- You can **toggle** a schedule off without deleting it — handy during an event.
- **Run it manually once** to confirm the tasks fire in the right order before
  relying on it.
- Check the schedule's **last run** status to confirm it's working.

## Troubleshooting

- **Didn't run:** confirm the schedule is enabled and the time fields are right
  (remember the panel's timezone).
- **Restarted at the wrong time:** adjust for timezone; the hour is in the panel's
  configured zone, not always yours.
- **Command did nothing:** check the exact command syntax in the console first (see
  *Using the game panel console*).
