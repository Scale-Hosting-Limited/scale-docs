---
title: Connecting with SFTP
slug: connecting-with-sftp
description: Use an SFTP client for fast, reliable file transfers to your game server.
---

The panel's file manager is fine for small edits, but for uploading a world,
a modpack, or lots of files, **SFTP** is faster and more reliable. It's a secure
file-transfer connection to your server.

## Get your SFTP details

Open your server in the panel and find the **SFTP** details (often on the file
manager or settings area). You'll get:

- **Host** and **port** (the SFTP port, which is usually **not** 22 — use the one
  shown).
- **Username** — often in the form `youraccount.serverid`.
- **Password** — your panel password, or a server-specific one shown there.

## Connect with a client

**FileZilla** (free, cross-platform) is the usual choice:

1. Download and open FileZilla.
2. Enter the **Host** as `sftp://host` (include `sftp://`), the **Port**,
   **Username**, and **Password**.
3. Click **Quickconnect**. Accept the host key the first time.
4. Your server's files appear on the right; your computer on the left. Drag files
   across to transfer.

Other good clients: WinSCP (Windows), Cyberduck (Mac/Windows), or the SFTP support
built into many code editors.

## What you can do

- **Upload** a world, modpack, or plugins folder far faster than the browser.
- **Download** backups of your world or configs to your computer.
- **Bulk edit** — pull configs down, edit locally, push them back.

## Tips

- **Stop the server** before replacing the world or large files, so nothing is
  written mid-transfer.
- Use `sftp://` in the host field — plain FTP is not offered (SFTP is encrypted).
- If a transfer of thousands of small files (like a region folder) is slow, zip it
  first, upload the zip, and extract it in the file manager.

## Troubleshooting

- **"Connection refused" / can't connect:** check you're using the **SFTP port**
  from the panel (not 22), and `sftp://` in the host.
- **Auth failed:** confirm the username format (`account.serverid`) and password;
  reset the password in the panel if unsure.
- **Permission denied writing files:** make sure you're in the server's directory
  and the server is stopped if you're replacing locked files.
