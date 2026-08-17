---
title: Setting up email DNS records
slug: setting-up-email-dns-records
description: Add MX, SPF, DKIM, and DMARC so your email delivers and doesn't get spoofed.
---

For email on your domain to work — and to actually land in inboxes rather than spam
— you need a handful of DNS records set correctly. Here's what each one does and how
to add it.

## The four records that matter

- **MX** — says *which mail server receives* email for your domain. Without it, mail
  to `you@yourname.com` has nowhere to go.
- **SPF** — a TXT record listing *who is allowed to send* mail as your domain.
- **DKIM** — a TXT record holding a signature key so receivers can verify your mail
  wasn't tampered with.
- **DMARC** — a TXT record telling receivers *what to do* if SPF/DKIM fail, and
  where to send reports.

Together, these prove your mail is genuine and stop others spoofing your domain.

## Where to add them

Go to **Domains → Manage → DNS** (see *Managing DNS records*). We'll show you the
exact values to use for our mail service — copy them in rather than guessing.

## MX record

- **Type:** MX
- **Name:** `@` (the domain itself)
- **Value:** our mail hostname (shown in your panel)
- **Priority:** as shown (lower number = higher priority)

If you're moving email to us, **remove old MX records** first so mail doesn't go to
the previous provider.

## SPF record

- **Type:** TXT
- **Name:** `@`
- **Value:** something like `v=spf1 include:<our-spf-host> ~all`

Only have **one** SPF record. If you send through other services too (e.g. a
newsletter tool), combine them into a single record with multiple `include:` parts —
don't add a second SPF record.

## DKIM record

- **Type:** TXT (or CNAME, depending on setup)
- **Name:** a selector like `<selector>._domainkey`
- **Value:** the key shown in your panel

DKIM values are long — paste carefully and don't add spaces or line breaks.

## DMARC record

- **Type:** TXT
- **Name:** `_dmarc`
- **Value:** start gentle, e.g. `v=DMARC1; p=none; rua=mailto:you@yourname.com`

Begin with `p=none` (monitor only), review the reports, then tighten to
`p=quarantine` and eventually `p=reject` once you're confident legitimate mail
passes.

## Check it worked

After adding the records and letting DNS propagate:

- Send a test email to a Gmail/Outlook account and check it doesn't land in spam.
- Use a mail-tester tool to confirm SPF, DKIM, and DMARC all pass.

## Troubleshooting

- **Mail going to spam:** almost always missing or wrong SPF/DKIM — recheck the
  values against your panel.
- **Two SPF records:** merge them into one; multiple SPF records is an error.
- **Nothing arriving:** check the MX record is present and points at our mail host,
  and old MX records are removed.

For more on inbox placement, see *Improving email deliverability*.
