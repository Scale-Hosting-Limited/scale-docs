---
title: Moving a server in from another host
slug: moving-a-server-in
description: Bring your existing game server across, by import tool or manual transfer.
---

Switching to us doesn't mean starting over. You can bring your existing world,
configs, plugins, and data across.

## Option 1: the built-in importer (SFTP pull)

If your service offers the **server import** tool, it pulls your files directly
from your old host over SFTP:

1. Open your new server and find **Import** (or **Transfer in**).
2. Enter your **old host's SFTP details** — host, port, username, and password or
   key — and the path to your server files.
3. **Connect** first: this logs in and counts the files and total size so you can
   confirm before anything is written. Nothing on your new server changes at this
   step.
4. Review the number, then **Import**. The transfer runs in the background — you can
   close the page.

The credentials for your old host are used only for the transfer and are cleared as
soon as it finishes. For security, the importer only connects to real, public
hosts.

## Option 2: manual transfer

If your old host doesn't offer SFTP, or you'd rather do it by hand:

1. On the **old** host, download your server files — at minimum the **world**
   folder, plus `plugins/`/`mods/`, and your config files (`server.properties`,
   plugin configs). Zipping them first makes it much faster.
2. On your **new** server, stop it, then upload the files via the file manager or
   SFTP (see *Connecting with SFTP*) and extract.
3. Match the **server type and version** to what you were running so the world and
   plugins load correctly.
4. Start the server and check the console reaches `Done`.

## After the move

- Update your **DNS/subdomain** so your old address (or a new one) points at the
  new server — see *Pointing your domain*.
- Tell your players the new address if it changed.
- Keep the old host active until you've confirmed everything works on ours, then
  cancel it.

## Troubleshooting

- **World didn't load:** the folder name must match `level-name` (default
  `world`), and shouldn't be nested inside an extra subfolder. See *Managing worlds
  and backups*.
- **Plugins/mods error on start:** version or loader mismatch — match the server
  type/version to the old setup.
- **Importer can't connect:** double-check the old host's SFTP host/port/username;
  the tool only reaches public servers, so a LAN-only address won't work.

Stuck mid-migration? Open a ticket with both sets of details (never your passwords)
and we'll help you get across.
