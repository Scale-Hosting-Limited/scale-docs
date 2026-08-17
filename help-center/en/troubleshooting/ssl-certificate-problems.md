---
title: SSL certificate problems
slug: ssl-certificate-problems
description: Fix "not secure" warnings, expired certificates, and mixed-content errors.
---

An SSL certificate is what puts the padlock in the browser and the `https://` on your
site. When it's misconfigured, visitors see scary "not secure" warnings. Here's how
to fix the common ones.

## "Your connection is not private" / "Not secure"

This means the browser can't validate your certificate. Usual causes:

- **No certificate installed** — you haven't enabled SSL yet. See *Enabling SSL /
  HTTPS*.
- **Certificate expired** — it lapsed and needs renewing (below).
- **Wrong domain** — the certificate is for a different name than the one being
  visited (e.g. covers `yourname.com` but not `www.yourname.com`).
- **DNS not pointing at us** — the domain resolves somewhere without your
  certificate. Check your records (see *Managing DNS records*).

## Certificate expired

Certificates are valid for a limited time and must renew.

- **Auto-renewing certificates** (like Let's Encrypt) usually renew themselves — if
  one didn't, it's often because DNS or the domain changed. Re-issue it from your
  hosting control panel.
- **Confirm the domain still points at us** so the renewal validation can succeed.
- After re-issuing, **clear your browser cache** or try a private window to see the
  new certificate.

## "Mixed content" warnings

Your page loads over HTTPS but pulls some resources (images, scripts, styles) over
plain HTTP. The padlock breaks or shows a warning.

1. **Update internal links** to `https://` (or protocol-relative/relative URLs).
2. In **WordPress**, set both the Site URL and Home URL to `https://`, and use a
   plugin or search-replace to fix old `http://` links in content.
3. **Check hard-coded resources** in your theme/templates.

## Redirect HTTP to HTTPS

Once your certificate works, force everyone onto the secure version:

- Enable the **"force HTTPS"** option in your control panel if available, or
- Add a redirect rule so `http://` requests go to `https://`.

This stops visitors ever landing on the insecure version.

## www vs non-www

A certificate must cover **every** name people use. If it covers `yourname.com` but
not `www.yourname.com`, visitors to `www` get a warning. Make sure your certificate
(and DNS) cover both, or redirect one to the other.

## After any certificate change

- **Wait a few minutes** for it to take effect.
- **Test in a private/incognito window** to avoid cached results.
- **Check with an SSL test tool** to confirm the full chain is valid.

## Still seeing warnings?

Open a ticket with: the **exact domain** (including www or subdomain), the **exact
warning text**, and a **screenshot**. Note whether you recently changed DNS or
re-issued the certificate — that's usually the clue (see *Opening a support ticket*).
