---
title: Installing WordPress
slug: installing-wordpress
description: Get WordPress running on your web hosting, by installer or manually.
---

WordPress powers a huge share of the web and runs well on standard hosting.
There are two ways to install it.

## Option 1: one-click installer

If your control panel includes an app installer (Softaculous or similar):

1. Open the installer and choose **WordPress**.
2. Pick the domain (and folder — leave blank to install at the root).
3. Set your **site title**, and an **admin username, password, and email**. Use a
   strong password and avoid `admin` as the username.
4. Install. The installer creates the database and files for you.

When it finishes you'll get links to your site and the `/wp-admin` dashboard.

## Option 2: manual install

1. **Create a database** and a database user, and note the name, user, and
   password (see *Managing MySQL databases*).
2. **Download WordPress** from wordpress.org and upload the files to your web root
   (`public_html`) via the File Manager or SFTP. Extract so `index.php` sits in
   the web root, not in a `wordpress/` subfolder.
3. Visit your domain — WordPress's setup wizard runs. Enter the database details
   from step 1 (host is usually `localhost`).
4. Set your site title and admin account and finish.

## First things to do

- **Log in** at `yourdomain.com/wp-admin`.
- **Set permalinks** (Settings → Permalinks → Post name) for clean URLs.
- **Enable HTTPS** — see *Enabling SSL / HTTPS*, then set your site URL to
  `https://` under Settings → General.
- **Install only trusted themes/plugins**, and keep them minimal.

## Keeping it secure and fast

- **Update** WordPress core, themes, and plugins promptly — outdated plugins are
  the #1 way WordPress sites get hacked.
- Use a strong admin password and enable 2FA with a security plugin.
- Fewer plugins = faster and safer. Remove ones you don't use (deactivate *and*
  delete).
- Take regular **backups** (a plugin, or your hosting backups) before big changes.

## Troubleshooting

- **"Error establishing a database connection":** wrong DB name/user/password in
  `wp-config.php`, or the wrong host. Re-check against your Databases section.
- **White screen:** usually a plugin or theme conflict — rename the `plugins`
  folder over SFTP to disable them all, then re-enable one at a time.
- **Stuck on `http://` / mixed content:** set both URLs to `https://` in Settings →
  General and use a plugin to fix mixed content if needed.
