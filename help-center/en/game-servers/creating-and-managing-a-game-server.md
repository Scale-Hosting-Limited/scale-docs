---
title: Creating and managing a game server
slug: creating-and-managing-a-game-server
description: Order a game server, find the panel, and learn the day-to-day controls.
---

Whatever game you're hosting — Rust, ARK, Valheim, Terraria, and more — the basics
are the same. This is your orientation to ordering a server and running it from the
game panel.

## Order your server

1. Pick the game and a plan sized for your player count and mods. RAM is usually the
   thing that matters most; more players and more mods need more.
2. Complete checkout. The server is provisioned automatically, usually within a few
   minutes.
3. When it's ready, open **Services → your server** to reach the **game panel**.

Not sure what size to get? See *Choosing the right plan*, and remember you can
upgrade later (see *Reinstalling or switching games* for bigger changes).

## The game panel at a glance

The panel is where you run the server day to day:

- **Console** — live output and a command line (see *Using the game panel
  console*).
- **Files** — browse, edit, upload, and download your server files.
- **Databases** — create databases some games/plugins need.
- **Schedules** — automate restarts and tasks (see *Scheduling restarts and
  tasks*).
- **Backups** — snapshot and restore your world/config (see *Backing up and
  restoring*).
- **Startup** — set the game version, world name, and options.
- **Settings** — SFTP details, reinstall, and more.

## Start, stop, restart

The main controls are at the top:

- **Start** boots the server.
- **Restart** stops and starts it — use after config changes.
- **Stop** shuts it down gracefully.
- **Kill** force-stops if it's hung — a last resort, as it can skip a clean save.

Watch the **console** as it starts; that's where you'll see it come online or report
an error.

## Connect and play

Your server's **address and port** are shown on the panel. Share them with players,
or point a subdomain at the server for a tidy address (see *Setting up a subdomain*).

## Managing files

Most configuration lives in text files you can edit directly in **Files**, or over
**SFTP** for bulk changes (see *Connecting with SFTP*). Always stop the server
before large file changes, then restart.

## Keeping it healthy

- **Restart on a schedule** — a daily restart clears memory and keeps things smooth.
- **Back up regularly** — before installing mods or big changes especially.
- **Watch resources** — see *Reducing lag and monitoring resources* if it struggles.

## Troubleshooting

- **Won't start:** read the console for the error; see *Server won't start*.
- **Can't connect:** check it's running and the address/port are right; see *Can't
  connect to your server*.
- **Laggy:** see *Reducing lag and monitoring resources*.
