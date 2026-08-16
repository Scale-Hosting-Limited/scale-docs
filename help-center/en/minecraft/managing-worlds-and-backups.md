---
title: Managing worlds and backups
slug: managing-worlds-and-backups
description: Upload, download, reset, and back up your Minecraft world safely.
---

Your world is the most important thing on your server. This guide covers moving it
in and out, resetting it, and keeping backups so a mistake or a corrupt chunk is
never the end of it.

## Where your world lives

On a standard server the world is the `world/` folder (plus `world_nether/` and
`world_the_end/` on some setups). The folder name is set by `level-name` in
`server.properties`.

## Back up your world

**Always stop the server before backing up** — copying a world while it's being
written can produce a corrupt copy.

- **From the panel:** if your plan includes backups, open the **Backups** tab and
  click **Create backup**. Restores are one click from the same place.
- **Manually:** in the File Manager, compress the `world` folder to a `.zip` and
  download it, or pull it down over SFTP (see *Connecting with SFTP*).

Keep at least one backup off the server (downloaded locally or to cloud storage).
A backup that only exists on the same server won't help if the whole instance has
a problem.

## Upload an existing world

Moving a world from single-player or another host:

1. Stop the server.
2. Zip your world folder locally.
3. Upload the zip in the File Manager and extract it, or upload the folder over
   SFTP.
4. Make sure the folder name matches `level-name` in `server.properties` (default
   `world`). If your upload is called `MyWorld`, either rename it to `world` or set
   `level-name=MyWorld`.
5. Start the server.

For **Bedrock** or **modded** worlds, keep the world's own folder structure intact
and match the server type/version to where the world came from.

## Reset / generate a new world

To start fresh:

1. Stop the server.
2. **Back up the current world first** if there's any chance you'll want it.
3. Delete (or rename) the `world`, `world_nether`, and `world_the_end` folders.
4. Start the server — it generates a new world on boot.

To change the seed for the new world, set `level-seed=<seed>` in
`server.properties` before starting.

## Downloading your world

You own your data. Stop the server, zip the world, and download it any time — from
the File Manager or over SFTP. If you cancel your service, download anything you
want to keep before it ends.

## Troubleshooting

- **World didn't load / a new one generated instead:** the folder name doesn't
  match `level-name`, or the upload extracted into a nested subfolder. Check the
  path is `world/level.dat`, not `world/world/level.dat`.
- **Corrupt chunks or "level.dat" errors:** restore your most recent good backup.
  This is exactly what backups are for — keep them regular.
- **Huge world, slow upload:** use SFTP rather than the browser File Manager for
  anything over a few hundred MB.
