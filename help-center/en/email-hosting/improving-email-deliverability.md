---
title: Improving email deliverability (SPF, DKIM, DMARC)
slug: improving-email-deliverability
description: Set the three DNS records that keep your mail out of spam folders.
---

If your mail lands in spam or bounces, the cause is almost always missing or wrong
authentication records. Three DNS records tell the world your mail is legitimate:
**SPF, DKIM, and DMARC**. Set all three.

## SPF — who's allowed to send

An SPF record lists the servers permitted to send mail for your domain. It's a
single TXT record on the root:

```
TXT  @  "v=spf1 include:<your-mail-host-spf> ~all"
```

Use the exact `include:` value from your email service page. **Only one SPF
record** per domain — if you send through several services, combine their includes
into one record.

## DKIM — a signature that proves it's really you

DKIM adds a cryptographic signature to your mail; receivers check it against a
public key in your DNS. Your email host gives you a DKIM record (a TXT record on a
selector name like `default._domainkey`):

```
TXT  default._domainkey  "v=DKIM1; k=rsa; p=<long public key>"
```

Copy it exactly — a single wrong character breaks the signature.

## DMARC — what to do with failures

DMARC tells receivers how to treat mail that fails SPF/DKIM, and where to send
reports. Start gentle and tighten later:

```
TXT  _dmarc  "v=DMARC1; p=none; rua=mailto:you@yourdomain.com"
```

`p=none` monitors without affecting delivery. Once SPF and DKIM are solid, move to
`p=quarantine` and eventually `p=reject` to stop spoofing of your domain.

## Check your setup

- Send a test to a Gmail account, open the message → **Show original**, and confirm
  **SPF: PASS** and **DKIM: PASS**.
- Or use a mail-tester tool that scores your setup and lists what's missing.

## Other deliverability tips

- **Match the From address to the domain** you authenticated — sending "from"
  another domain undoes SPF/DKIM.
- **Warm up gradually** — a brand-new domain suddenly sending lots of mail looks
  like spam. Ramp volume up over days.
- **Don't send unsolicited bulk mail.** Aside from the rules, it wrecks your
  reputation and gets the sending IP blocked.
- **Keep content clean** — misleading subject lines and spammy phrasing hurt
  scoring even with perfect DNS.

## Troubleshooting

- **Everything goes to spam:** SPF/DKIM likely failing — recheck the records match
  your host's values exactly, and that there's only one SPF record.
- **Bounces mentioning SPF/DKIM/DMARC:** the specific record named is wrong or
  missing.
- **Was fine, now failing:** a DNS change may have removed a record, or you started
  sending from a new service not in your SPF.
