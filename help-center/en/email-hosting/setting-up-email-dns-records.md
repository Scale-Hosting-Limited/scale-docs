---
title: Setting up email DNS records
slug: setting-up-email-dns-records
description: Add MX, SPF, DKIM, and DMARC so your mailboxes send and receive reliably.
---

For email on your domain to work properly, your domain needs the right DNS records
pointing at our mail service. Without them, mail won't arrive — or worse, it arrives
in spam. Here's what to add and why. (This mirrors the domains guide of the same name
so you can find it from either section.)

## The records you need

- **MX** — tells the internet **which server receives** your mail.
- **SPF** — a TXT record listing **who may send** as your domain.
- **DKIM** — a TXT record with a signature key so receivers can **verify** your mail.
- **DMARC** — a TXT record telling receivers **what to do** if SPF/DKIM fail.

Together they make your mail deliverable and stop others spoofing your domain.

## Where to add them

If your DNS is managed here, go to **Domains → Manage → DNS** (see *Managing DNS
records*). We'll show the exact values for our mail service — copy them rather than
guessing. If your domain's nameservers are elsewhere, add the records at that
provider instead (see *Nameservers explained*).

## MX record

- **Type:** MX · **Name:** `@` · **Value:** our mail hostname · **Priority:** as
  shown.
- **Remove old MX records** if you're moving from another provider, so mail doesn't
  keep going there.

## SPF record

- **Type:** TXT · **Name:** `@` · **Value:** e.g. `v=spf1 include:<our-spf-host>
  ~all`.
- Keep **only one** SPF record. If you also send via other services, combine them
  into a single record with multiple `include:` parts.

## DKIM record

- **Type:** TXT (or CNAME) · **Name:** the selector shown (like
  `<selector>._domainkey`) · **Value:** the key from your panel.
- DKIM keys are long — paste carefully, no added spaces or breaks.

## DMARC record

- **Type:** TXT · **Name:** `_dmarc` · **Value:** start with `v=DMARC1; p=none;
  rua=mailto:you@yourname.com`.
- Begin at `p=none` (monitor), review reports, then tighten to `quarantine` and
  eventually `reject`.

## Confirm it works

After the records propagate:

- Send a test to a Gmail/Outlook account and check it lands in the inbox.
- Use a mail-tester tool to confirm SPF, DKIM, and DMARC all pass.

## Troubleshooting

- **Mail in spam:** almost always missing/wrong SPF or DKIM — recheck against your
  panel; see *Improving email deliverability*.
- **Nothing arriving:** confirm the MX record is present and old ones removed.
- **Two SPF records:** merge into one; multiple SPF records is invalid.

For diagnosing live problems, see *Email not sending or receiving*.
