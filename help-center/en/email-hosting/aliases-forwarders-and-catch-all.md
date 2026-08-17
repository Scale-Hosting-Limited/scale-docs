---
title: Aliases, forwarders, and catch-all
slug: aliases-forwarders-and-catch-all
description: Create extra addresses, forward mail elsewhere, and catch everything else.
---

You don't need a separate mailbox for every address. Aliases, forwarders, and a
catch-all let one mailbox handle many addresses — great for `info@`, `sales@`,
`support@`, and personal setups.

## Alias vs forwarder vs mailbox

- **Mailbox** — a real inbox with its own storage and login (see *Creating a
  mailbox*).
- **Alias** — an extra address that **delivers into an existing mailbox**. No new
  login, no extra storage.
- **Forwarder** — sends mail on to **another address**, often external (e.g. your
  Gmail).
- **Catch-all** — receives mail sent to **any address** on your domain that doesn't
  otherwise exist.

Aliases and forwarders are free ways to look bigger and stay organised without paying
for extra mailboxes.

## Create an alias

Use aliases to give one mailbox several public addresses.

1. In your email panel, open **Aliases** (or **Email Accounts → Aliases**).
2. Enter the **alias address** (e.g. `sales@yourname.com`).
3. Choose the **destination mailbox** it should deliver into.
4. Save. Mail to the alias now lands in that mailbox.

Common set: `info@`, `sales@`, `support@`, `hello@` all feeding one mailbox you
actually check.

## Set up a forwarder

Forward mail to an address elsewhere.

1. Open **Forwarders**.
2. Enter the **source address** on your domain.
3. Enter the **destination** address to forward to.
4. Save.

You can forward to more than one destination, and combine forwarding with keeping a
copy in the local mailbox if the option is offered.

> **Forwarding and deliverability:** forwarding to Gmail/Outlook can sometimes trip
> spam filters, because the forwarded mail arrives via your server. Proper SPF/DKIM
> helps (see *Setting up email DNS records*).

## Catch-all

A catch-all grabs mail to **any** address at your domain that doesn't exist —
`anything@yourname.com`.

- **Upside:** you never miss a mistyped address, and you can invent addresses on the
  fly.
- **Downside:** it also catches **spam** aimed at random addresses, which can be a
  lot.

Enable it under **Catch-all** and point it at a mailbox. Many people prefer specific
aliases over a catch-all for exactly the spam reason.

## Which should I use?

- Want another public address into your existing inbox → **alias**.
- Want mail to go to an external inbox → **forwarder**.
- Want to never miss any address → **catch-all** (mind the spam).
- Need a separate, logged-in inbox with its own storage → **mailbox**.

## Troubleshooting

- **Alias mail not arriving:** confirm the destination mailbox exists and isn't full
  (see *Managing mailbox storage*).
- **Forwarded mail bouncing/spam:** check SPF/DKIM; some providers reject forwarded
  mail — see *Email not sending or receiving*.
- **Catch-all flooded with spam:** switch to specific aliases instead.
