---
title: Using the file manager
slug: using-the-file-manager
description: Manage your website files right in the browser — no FTP client needed.
---

The file manager in your hosting control panel lets you upload, edit, and organise
your website files straight from the browser. It's perfect for quick changes without
setting up an FTP client.

## Open the file manager

In your hosting control panel, open **File Manager**. It shows your account's files
and folders. For a website, the important one is the **web root** — usually
**`public_html`** (or `www` / `htdocs`) — which is what visitors actually see.

## Getting around

- **Double-click a folder** to open it.
- Use the **path/breadcrumb** at the top to see where you are and jump back.
- Your site's files belong **inside** the web root, not above it.

## Common tasks

- **Upload:** click **Upload** and select files, or drag them in. For a whole site,
  upload a **zip** and extract it (below) — much faster than many small files.
- **Create:** make a new **file** or **folder** for organising content.
- **Edit:** open a text/code file in the built-in editor, change it, and save — great
  for a quick tweak to `index.html`, a config, or a `.htaccess` file.
- **Rename / move / copy:** right-click (or use the toolbar) to rename, or
  drag/cut-paste to move files between folders.
- **Delete:** remove files you don't need — carefully, as this is usually permanent.
- **Download:** pull a copy of a file or folder to your computer.

## Zip and unzip

For anything large:

1. **Upload a zip** of your site.
2. Select it and choose **Extract** to unpack it in place.
3. Delete the zip afterwards to save space.

You can also **compress** a folder to a zip before downloading — handy for a quick
backup (see *Backing up and restoring your site*).

## Show hidden files

Files starting with a dot (like **`.htaccess`**) are hidden by default. Turn on
**show hidden files** in the settings to see and edit them — `.htaccess` controls
redirects, HTTPS forcing, and more.

## File manager vs SFTP

- **File manager** — quick edits, small uploads, no setup. Best for occasional
  changes.
- **SFTP** — bulk transfers, folder syncing, editing in your own tools. Best for
  developers and big sites (see *Connecting with FTP and SFTP*).

Use whichever fits the job; they act on the same files.

## Safety tips

- **Back up before big edits** — download a copy first, or zip the folder.
- **Don't delete files you don't recognise** in the web root — some are needed by
  your app or CMS.
- **Mind file permissions** — wrong permissions can break a site or expose it;
  defaults are usually right, so change them only when a guide tells you to.

## Troubleshooting

- **Site not updating:** confirm you edited the file in the **web root**, and clear
  your browser cache.
- **Can't see `.htaccess`:** enable **show hidden files**.
- **Upload fails for a big file:** zip it, or use SFTP instead (see *Connecting with
  FTP and SFTP*).
- **Edited the wrong thing:** restore from a backup (see *Backing up and restoring
  your site*).
