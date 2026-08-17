---
title: Backing up and restoring your site
slug: backing-up-and-restoring-your-site
description: Keep copies of your website and database, and roll back when needed.
---

A website is files **plus** a database, and a proper backup captures both. Get into
the habit and a hack, a bad update, or a fat-fingered edit becomes a quick restore
instead of a disaster. Here's how.

## What a full backup includes

- **Files** — everything in your web root (`public_html`): code, themes, plugins,
  uploads.
- **Database** — the content and settings for apps like WordPress (posts, users,
  configuration).

Miss either and your restore is incomplete — files without the database (or vice
versa) won't give you a working site.

## Back up your files

- **Via the file manager:** compress your web root to a **zip** and download it (see
  *Using the file manager*).
- **Via SFTP:** download your site folder to your computer (see *Connecting with FTP
  and SFTP*).
- **Via a control-panel backup** tool, if your plan includes one — often the easiest.

## Back up your database

1. Open **phpMyAdmin** (or the database tool) from your control panel.
2. Select your database and choose **Export**.
3. Download the **`.sql`** file.

See *Managing MySQL databases* for detail. Keep the database dump alongside your file
backup so the pair stays together.

## Automate it

Manual backups get forgotten. Automate where you can:

- Use your control panel's **scheduled backups** if available.
- Or set a **cron job** to dump the database and archive files on a schedule (see
  *Setting up cron jobs*).
- For apps like WordPress, a reputable **backup plugin** can schedule and store
  backups off-site.

Aim for regular backups plus an extra one **before any risky change**.

## Restore your files

1. Upload your backup zip to the web root and **extract** it (see *Using the file
   manager*), or push the files back over SFTP.
2. Overwrite the broken files with the good ones.
3. Load the site and check it works.

To recover **just one file**, extract the backup locally and upload only that file —
no need to roll everything back (see *Restoring from a backup*).

## Restore your database

1. In **phpMyAdmin**, select the database.
2. Use **Import** and choose your `.sql` backup.
3. If needed, drop the existing tables first so the import is clean (be sure — this
   overwrites current data).

## Keep backups safe and current

- **Store off-site** — a backup only on the same server isn't much protection.
  Download copies to your computer or cloud storage.
- **Keep a few generations** — the newest isn't always the one you want if a problem
  went unnoticed for a while.
- **Test a restore** occasionally — a backup you've never restored is a guess.

## Troubleshooting

- **Restored files but site's still broken:** you probably also need to restore the
  **database** — restore both from the same point in time.
- **Database import fails:** it may be too large for the web import; ask us or import
  in parts.
- **Site shows old content after restore:** clear caches (browser, and any caching
  plugin).
- **No backup and a broken site:** open a ticket — we'll help where we can, but this
  is exactly why regular backups matter (see *Opening a support ticket*).
