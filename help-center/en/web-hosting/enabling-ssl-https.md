---
title: Enabling SSL / HTTPS
slug: enabling-ssl-https
description: Get the padlock on your site and force secure connections.
---

HTTPS encrypts traffic between your visitors and your site, shows the padlock, and
is expected by browsers and search engines. On our hosting it's free and mostly
automatic.

## How certificates are issued

Most plans include a free **Let's Encrypt** certificate that issues automatically
once your domain **points to the server** (see *Pointing your domain*). If your
domain resolves to us, the certificate typically appears within a few minutes and
renews itself.

If it hasn't appeared:

- Confirm the domain's DNS points to the server IP shown on your service page.
- Check the **SSL/TLS** section of your control panel — you can usually trigger
  issuance manually there once DNS is correct.

## Force HTTPS

Having a certificate isn't enough — send visitors to the secure version:

- Many control panels have a **"Force HTTPS"** toggle — use it if present.
- Otherwise add a redirect in `.htaccess` at your web root:

```
RewriteEngine On
RewriteCond %{HTTPS} off
RewriteRule ^(.*)$ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

- **WordPress:** set both URLs to `https://` under Settings → General, then add
  the redirect above (or use a plugin).

## Fixing "Not secure" or mixed content

- **"Not secure" / no padlock:** the certificate isn't issued yet or the domain
  isn't fully pointed. Recheck DNS and issuance.
- **Padlock with a warning (mixed content):** the page loads over HTTPS but pulls
  some images/scripts over `http://`. Update those links to `https://` (or
  protocol-relative). For WordPress, a mixed-content-fix plugin handles most of it.

## Certificate renewal

Let's Encrypt certificates last 90 days and renew automatically as long as your
domain keeps pointing to the server. You don't need to do anything — but if you
change hosts or DNS, make sure the domain still resolves to us so renewal
continues.

## Custom / purchased certificates

If you have a certificate from another provider, you can usually install it in the
control panel's SSL/TLS section by pasting the certificate, key, and CA bundle. For
most people the free automatic certificate is all you need.

If HTTPS still won't come up after DNS is confirmed correct, open a ticket with
your domain and we'll issue it manually.
