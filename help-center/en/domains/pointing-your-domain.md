---
title: Pointing your domain to your service
slug: pointing-your-domain
description: Connect a domain you own to your web hosting or game server.
---

Pointing a domain means telling the internet that your name (like
`example.com`) leads to your service with us. How you do it depends on the service.

## Web hosting

You have two options at your domain registrar:

**Option A — nameservers (simplest).** Set your domain's nameservers to the ones
shown on your hosting service page. This hands all DNS to us, and records like
`www` and mail are configured for you. Best if you want it to "just work."

**Option B — an A record.** Keep your current DNS and add:

- an **A record** for `@` pointing to the IP shown on your service page, and
- a **CNAME** (or second A record) for `www` pointing to your domain.

Changes take a little time to propagate — usually minutes, sometimes a few hours.

## Game servers (Minecraft and others)

Players don't like typing an IP and port. You can give them a clean address:

- **Minecraft (Java):** create an **SRV record** so `play.example.com` resolves to
  your IP *and* port, letting players connect without typing the port. Many hosts
  and our panel's address tool can set this up for you — see the server's
  **Address**/**Subdomain** tab.
- **A record:** if your server uses the default port, a simple A record for a
  subdomain (e.g. `mc.example.com` → your IP) is enough and players connect with
  just that name.

If you'd rather not manage DNS yourself, the panel can give you a free subdomain
(like `yourname.play.scale…`) with one click.

## After you point it

- **Web:** once DNS resolves to the server, your site loads on the domain and an
  SSL certificate is issued automatically (see *Enabling SSL / HTTPS*).
- **Game:** add the server in Minecraft using your new address.

## Troubleshooting

- **Still shows the old site / doesn't resolve:** DNS hasn't propagated yet, or the
  record is wrong. Check with a DNS lookup tool that the A record matches the IP on
  your service page.
- **Works without `www` but not with it (or vice-versa):** you're missing the `www`
  record — add both.
- **Minecraft won't connect on the domain but works on the IP:port:** the SRV
  record is missing or wrong; double-check the priority/weight/port fields.

See *Managing DNS records* for the details of each record type.
