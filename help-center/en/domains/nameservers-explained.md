---
title: Nameservers explained
slug: nameservers-explained
description: What nameservers do, when to change them, and how to point them at us.
---

Nameservers decide **who answers questions about your domain** — where its website
lives, where its email goes, and so on. Getting them right is the foundation of
everything else, so it's worth understanding the basics.

## What a nameserver actually does

When someone visits your domain, their computer asks, "Where does this domain
point?" That question goes to your domain's **nameservers**, which hold the DNS
records (A, CNAME, MX, TXT…) and hand back the answers.

So the nameservers control **which set of DNS records is used**. Whoever runs your
nameservers is where you edit your DNS.

## Two ways to manage DNS

There are two common setups, and it helps to know which you're on:

1. **Use our nameservers** (simplest). You point your domain at Scale Hosting's
   nameservers, and you manage all DNS records right here in the panel (see
   *Managing DNS records*). Best if your domain is registered with us or you want
   everything in one place.
2. **Use someone else's nameservers.** Your domain points at another DNS provider
   (e.g. Cloudflare, or another registrar), and you manage records there instead.
   Valid too — just remember your records live wherever the nameservers point.

You can only use **one** set of nameservers at a time, and that set decides where
you edit DNS.

## Point your domain at our nameservers

1. Find our nameserver addresses in **Domains → Manage** (they look like
   `ns1.…` and `ns2.…`).
2. At **whoever your domain is registered with**, open the domain's nameserver
   settings.
3. Replace the existing nameservers with ours.
4. Save. The change can take anywhere from a few minutes to **48 hours** to fully
   propagate worldwide.

If your domain is registered with us, this is already set for you.

## Important: changing nameservers can move your DNS

When you switch nameservers, the domain starts using the **new** provider's records
— which may be empty. To avoid downtime:

- **Set up your DNS records at the new provider first** (A, CNAME, MX, TXT).
- **Then** change the nameservers.

Otherwise your site and email can drop while you scramble to recreate records.

## Nameservers vs DNS records — the difference

- **Nameservers** = *which provider* answers for your domain.
- **DNS records** = the *actual answers* (this domain → this IP, this mail → this
  server).

Change nameservers to switch providers; change DNS records to point services around
within a provider.

## Troubleshooting

- **Changes not taking effect:** propagation takes time — wait, then re-check.
- **Site/email went down after a change:** your records probably didn't come across;
  recreate them at the active nameserver provider.
- **Not sure which nameservers you're on:** a WHOIS lookup or your registrar's
  domain page shows the current nameservers.
