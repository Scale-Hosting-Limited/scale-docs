---
title: Your website isn't loading
slug: website-not-loading
description: Diagnose blank pages, errors, and DNS problems on your web hosting.
---

A site that won't load usually comes down to DNS, files, or a server-side error.
Here's how to narrow it down.

## Is it DNS or the site?

First work out whether visitors are even reaching the server:

- If you **just pointed your domain**, DNS can take a little while to propagate
  (usually minutes, sometimes hours). Try the temporary URL from your service page,
  or check with a DNS lookup tool that your domain's A record points at the IP the
  panel shows.
- If the temporary URL works but your domain doesn't, it's a **DNS** problem — see
  *Pointing your domain* and *Managing DNS records*.

## Blank white page

- Usually a **PHP error** with display turned off. Check your app's error log (and
  the server error log in the control panel) for the real message.
- For WordPress, enable `WP_DEBUG` temporarily, or rename the `plugins` folder to
  rule out a broken plugin.

## "500 Internal Server Error"

- Check the **error log** in your control panel — it names the cause.
- Common causes: a bad line in `.htaccess` (rename it to test), a wrong **PHP
  version** for your app, or a permissions problem on files/folders.

## "403 Forbidden"

- Missing index file — make sure your homepage is `index.html` or `index.php` in
  the web root (`public_html`).
- Directory permissions too strict, or an `.htaccess` `deny` rule.

## "404 Not Found" for everything

- Files aren't in the **web root**, or they extracted into a subfolder. The path
  should be `public_html/index.php`, not `public_html/mysite/index.php`.
- For frameworks using pretty URLs, confirm `mod_rewrite`/`.htaccess` is in place.

## Database connection errors

- The app's config has the wrong database name, user, or password. Re-check them
  against the **Databases** section (see *Managing MySQL databases*).
- Use `localhost` (or the host the panel specifies) as the database host.

## Certificate / "Not secure" warnings

- The SSL certificate hasn't been issued yet, or the domain isn't fully pointed.
  See *Enabling SSL / HTTPS*. Certificates issue automatically once the domain
  resolves to the server.

## Still down?

Open a ticket with your domain, the exact error or a screenshot, and whether the
temporary URL works. Knowing whether the temp URL loads tells us immediately
whether it's DNS or the site itself.
