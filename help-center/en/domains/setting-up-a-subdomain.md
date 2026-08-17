---
title: Setting up a subdomain
slug: setting-up-a-subdomain
description: Create subdomains like play. or shop. to point at different services.
---

A subdomain is a prefix on your domain — `play.yourname.com`, `shop.yourname.com`,
`mail.yourname.com`. They're free, you can make as many as you like, and each can
point somewhere different. They're perfect for giving a game server, a shop, or a
staging site its own tidy address.

## When to use one

- **`play.yourname.com`** → your Minecraft or game server, so players type a name
  instead of an IP and port.
- **`shop.` / `store.`** → a separate store or panel.
- **`dev.` / `staging.`** → a test copy of your site.
- **`mail.` / `webmail.`** → your email service.

## Create a subdomain with DNS

A subdomain is just a DNS record on your existing domain.

1. Go to **Domains → Manage → DNS** (see *Managing DNS records*).
2. Add a record for the prefix:
   - **A record** — name `play`, value the server's **IP address**.
   - or **CNAME** — name `shop`, value another hostname (e.g. `yourname.com`).
3. Save. It becomes live once DNS propagates (usually minutes, up to a couple of
   hours).

You only enter the prefix (`play`), not the whole thing — the panel adds your
domain automatically.

## Subdomains for game servers

Game servers often run on a non-standard port. Two common approaches:

- **A record + tell players the port:** `play.yourname.com:25565`.
- **SRV record** (best for Minecraft): lets players connect with just
  `play.yourname.com`, no port needed. Add an SRV record pointing the service to
  your host and port. See *Pointing your domain* and your game's guide.

## Subdomains for web hosting

On a web hosting plan you can also create a subdomain that maps to a **folder**, so
`blog.yourname.com` serves files from a `blog` directory. Look for **Subdomains**
in your hosting control panel; it creates the DNS and the folder together.

## Tips

- **Wildcards:** a `*` record (`*.yourname.com`) catches every subdomain you
  haven't defined — handy, but use it deliberately.
- **SSL:** subdomains need their own HTTPS coverage. A wildcard certificate secures
  all of them at once (see *Enabling SSL / HTTPS*).
- **No extra cost:** subdomains are part of your domain — you're never charged per
  subdomain.

## Troubleshooting

- **Not resolving:** give DNS time to propagate; double-check the record name is
  just the prefix and the value is correct.
- **Wrong destination:** make sure you used an A record for an IP and a CNAME for a
  hostname — mixing them up is the usual cause.
