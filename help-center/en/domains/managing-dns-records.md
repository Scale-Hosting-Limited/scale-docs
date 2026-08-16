---
title: Managing DNS records
slug: managing-dns-records
description: What each DNS record type does and how to set them correctly.
---

DNS records are the instructions that turn your domain into addresses for
websites, mail, and game servers. You manage them wherever your DNS is hosted —
your registrar, or our panel if you're using our nameservers.

## The record types you'll use

**A** — points a name to an **IPv4 address**.
`@ → 123.45.67.89` sends your bare domain to that server.

**AAAA** — same as A, but for an **IPv6 address**.

**CNAME** — points a name to **another name** (an alias).
`www → example.com`. A CNAME can't be used on the root (`@`) domain.

**MX** — where **email** for the domain is delivered. Has a priority (lower =
preferred). Set these from your email host (see *Creating a mailbox*).

**TXT** — free-form text, used for verification and email security records like
**SPF**, **DKIM**, and **DMARC** (see *Improving email deliverability*).

**SRV** — points a **service** (with a port) to a host. Used to give Minecraft:
Java a clean address without a port number.

## Anatomy of a record

- **Type** — A, CNAME, MX, TXT, SRV…
- **Name / host** — the subdomain. `@` means the root domain; `www` means
  `www.example.com`.
- **Value / target** — the IP or name it points to.
- **TTL** — how long resolvers cache it (seconds). 3600 (1 hour) is fine; lower it
  to 300 before a planned change so it updates faster.

## Common setups

**Website on the root and www:**
```
A      @     123.45.67.89
CNAME  www   example.com
```

**Minecraft Java clean address (SRV):**
```
A    play          123.45.67.89
SRV  _minecraft._tcp.play   →  priority 0, weight 5, port 25565, target play.example.com
```

**Email (from your mail host's instructions):**
```
MX   @    mail.example.com   (priority 10)
TXT  @    "v=spf1 include:… ~all"
TXT  …    DKIM key
```

## Tips and gotchas

- **Propagation:** changes aren't instant. Allow minutes to a few hours; lowering
  TTL beforehand speeds later changes up.
- **Don't duplicate conflicting records** — two A records for `@` pointing at
  different IPs will load-balance unpredictably.
- **CNAME at the root won't work** — use an A record (or an ALIAS/ANAME if your
  provider offers one).
- **Verify with a lookup tool** after changes so you're not guessing.

If you use our nameservers, you can manage all of this from the panel; if your DNS
is elsewhere, make the same records at that provider.
