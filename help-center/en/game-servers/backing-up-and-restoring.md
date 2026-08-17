---
title: Backing up and restoring
slug: backing-up-and-restoring
description: Snapshot your server and roll back safely when something goes wrong.
---

Backups are your safety net. Whether a mod update breaks the world, a player grief's
the map, or a config change goes sideways, a recent backup turns a disaster into a
five-minute fix. Here's how to use them well.

## Create a backup

1. In the game panel, open **Backups**.
2. Click **Create backup** and give it a name that means something later — e.g.
   "before-modpack-update".
3. Wait for it to finish. Large worlds take longer; don't restart mid-backup.

Each backup is a snapshot of your server files at that moment.

## Automate them

Doing it by hand means you'll forget. Set a **scheduled backup** so you always have
a recent one (see *Scheduling restarts and tasks*). A daily backup is a sensible
baseline; back up more often around big changes or busy events.

## Back up before risky changes

Always take a fresh backup **before**:

- Installing or updating mods, plugins, or a modpack.
- Changing major server settings or the game version.
- Any bulk file edits over SFTP.

That way, if it goes wrong, you're one restore away from where you started.

## Restore a backup

1. Open **Backups** and find the one you want.
2. Choose **Restore**. This **overwrites current files** with the backup, so be
   sure — and consider backing up the *current* state first if there's anything
   worth keeping.
3. Wait for it to complete, then **start** the server and check the console.

The server must usually be **stopped** to restore. Restoring rolls everything back
to that snapshot — recent progress after the backup point is lost, which is exactly
the point.

## Download a backup

You can **download** a backup to keep an off-site copy on your own computer — smart
for irreplaceable worlds. Store it somewhere safe; it's your independent copy if you
ever need it.

## Backup limits and retention

Plans include a certain number of backup slots. When you hit the limit:

- **Delete old backups** you no longer need, or
- **Download and remove** older ones to keep an archive without using slots.

Keep at least a couple of recent, known-good backups at all times.

## Troubleshooting

- **Backup failed:** the world may be too large for the slot, or the server was
  busy — try again when it's idle, and remove old backups to free space.
- **Restore didn't take:** make sure the server was fully stopped, then restarted
  after the restore.
- **Lost progress after restore:** that's expected — a restore returns you to the
  snapshot; there's no undo, so restore deliberately.
