---
title: Restoring from a backup
slug: restoring-from-a-backup
description: Roll back to a working state after a bad change, crash, or corruption.
---

When something's gone badly wrong — a broken update, a corrupted world, a hacked
site, or a change you can't undo — restoring a backup is usually the fastest way back
to normal. This is the general recovery playbook.

## When to restore

Restore a backup when:

- A **mod/plugin or config change** broke things and you can't unpick it.
- Your **world, database, or files are corrupted** (often after a crash or full
  disk).
- Your **site was defaced or compromised** and you want a clean known-good copy.
- You simply want to **undo recent changes** wholesale.

A restore rolls everything back to the snapshot — so anything created **after** that
snapshot is lost. That's the point, but be sure before you commit.

## Before you restore

1. **Pick the right backup.** Choose the most recent one from *before* the problem
   started — not after.
2. **Back up the current (broken) state too**, if there's anything in it you might
   still want (a recent build, new data). You can pull files out of it later.
3. **Stop the service** — most restores need it stopped (see your product's backup
   guide).

## How to restore

The exact steps depend on the product, but broadly:

1. Open **Backups** in your panel (game server / hosting control panel).
2. Find the backup you want and choose **Restore**.
3. Confirm — this **overwrites** current files with the backup.
4. Wait for it to finish, then **start** the service and check it works.

See *Backing up and restoring* for game servers and *Backing up and restoring your
site* for web hosting.

## Restoring specific files only

Sometimes you don't want a full rollback — just one file or folder back:

1. **Download** the backup rather than restoring it wholesale.
2. Extract it on your computer.
3. Upload **only the file(s)** you need over SFTP or the file manager (see
   *Connecting with SFTP* / *Using the file manager*).

This recovers a single broken config without losing everything since.

## Databases

Website and app data often lives in a **database**, not just files. A full recovery
may need **both** the files and a database backup restored together. See *Managing
MySQL databases* for importing a database dump.

## After restoring

- **Check it actually works** — load the site or start the server and watch the logs
  (see *Reading server logs*).
- **Re-apply only the good changes** you lost, carefully, testing as you go.
- **Fix the root cause** so you don't just restore into the same problem — if a mod
  broke it, don't reinstall that mod unchanged.

## No backup?

If you have nothing to restore, recovery is much harder — which is the whole argument
for **automating backups now** (see *Scheduling restarts and tasks*). Some
corruption has repair tools; open a ticket and we'll advise, but we can't recover
data that was never backed up.
