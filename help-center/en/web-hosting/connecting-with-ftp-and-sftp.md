---
title: Connecting with FTP and SFTP
slug: connecting-with-ftp-and-sftp
description: Upload and manage your website files with an FTP/SFTP client.
---

For anything more than the odd file, an FTP/SFTP client is the fastest way to manage
your website — drag whole folders across, edit in bulk, and keep a local copy in
sync. Here's how to connect and use one safely.

## FTP vs SFTP — use SFTP

- **FTP** is the old standard and sends your **password in the clear** — avoid it
  where possible.
- **SFTP** does the same job over an **encrypted** connection. Always prefer SFTP.

If your plan offers SFTP (or FTP over TLS/FTPS), use the secure option. Only fall
back to plain FTP if there's truly no alternative.

## What you'll need

Find these in your hosting control panel (often **FTP Accounts** or the service
details):

- **Host** — the server address (a hostname or IP).
- **Username** — your FTP/SFTP username.
- **Password** — set or shown in the panel.
- **Port** — typically `22` for SFTP, `21` for FTP.

## Connect with a client

A free client like **FileZilla** works well.

1. Open your client and create a new connection/site.
2. Enter the **host, username, password, and port**.
3. Choose the **protocol** — SFTP if available.
4. Connect. You'll see your **local files** on one side and the **server** on the
   other.

## Where to put your website

Website files usually go in a specific folder — commonly **`public_html`** (or
`www`, or `htdocs`). Upload your site **inside** that folder, not above it, or it
won't be served. Your control panel documents the exact web root.

## Uploading and downloading

- **Upload:** drag files/folders from the local side to the server side.
- **Download:** drag the other way to pull a copy to your computer.
- **Edit:** many clients let you open a file, edit it, and save it straight back.

For big sites, upload a **zip** and extract it in the file manager — far faster than
thousands of individual files (see *Using the file manager*).

## Security tips

- **Prefer SFTP** over FTP so credentials aren't sent in the clear.
- **Use a strong FTP password** and don't reuse it (see *Keeping your account
  secure*).
- **Create separate FTP accounts** for other people rather than sharing your main
  one, and remove them when no longer needed.
- **Don't store the password** on shared computers.

## Troubleshooting

- **Can't connect:** double-check host, port, and protocol; confirm the credentials
  in your panel; try SFTP on port 22.
- **Connected but no files/wrong folder:** make sure you're in the web root
  (`public_html`) — that's where your site lives.
- **Uploads slow or dropping:** upload a zip and extract it server-side; check your
  local connection.
- **"Permission denied":** the file/folder permissions may be wrong — see your
  control panel or open a ticket (see *Opening a support ticket*).
