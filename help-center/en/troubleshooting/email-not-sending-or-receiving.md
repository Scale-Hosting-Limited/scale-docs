---
title: Email not sending or receiving
slug: email-not-sending-or-receiving
description: Diagnose email that won't send, won't arrive, or lands in spam.
---

Email problems fall into a few clear buckets: it won't send, it won't receive, or it
sends but lands in spam. Work through the checks for your symptom and you'll find the
cause.

## Not receiving email

If mail to your address isn't arriving:

1. **Check your MX record.** Without a correct MX record, incoming mail has nowhere
   to go. Confirm it points at our mail host (see *Setting up email DNS records*).
2. **Check the mailbox exists** and isn't full — a full mailbox rejects new mail (see
   *Managing mailbox storage*).
3. **Check spam/junk** in your mail app, and any filters or rules you've set.
4. **Test from an outside address** (e.g. Gmail) and see if it bounces — a bounce
   message says why.

## Not sending email

If you can't send:

1. **Check your client settings** — outgoing (SMTP) server, port, and that
   authentication is on (see *Connecting your email client*).
2. **Use the right port and encryption** — typically SMTP on the secure port with
   SSL/TLS. Wrong port or "no encryption" is a common cause.
3. **Confirm your password** — an app that stopped sending after a password change
   needs the new one.
4. **Check you're not over a sending limit** — sudden bulk sending can trip limits.

## Sending, but landing in spam

If your mail arrives in recipients' spam folders, it's almost always
**authentication**:

1. **Set up SPF, DKIM, and DMARC** correctly — this is the number-one fix for spam
   placement (see *Setting up email DNS records*).
2. **Check your domain/IP isn't on a blocklist** — a mail-tester tool will tell you.
3. **Warm up gradually** — sending a large volume from a brand-new domain looks
   suspicious; build up over time.
4. **Write like a human, not a spammer** — avoid spammy subject lines and all-caps.

For the full deliverability picture, see *Improving email deliverability*.

## Webmail works but my app doesn't (or vice versa)

- **Webmail works, app doesn't** → the problem is your client's settings (server,
  port, password). Recheck them (see *Connecting your email client*).
- **App works, webmail doesn't** → try another browser, clear cache; see *Accessing
  webmail*.

## Reading a bounce message

When mail fails, you often get a **bounce** back. Read it:

- **"Mailbox full"** → clear space or upgrade storage.
- **"User unknown"/"No such user"** → the address is wrong or doesn't exist.
- **"Blocked"/"blacklisted"** → a reputation/blocklist issue; see deliverability
  above.
- **"Relay denied"** → authentication isn't set up on your outgoing mail.

## Still stuck?

Open a ticket with: the **exact error or bounce message**, whether it's send/receive,
whether **webmail** works, and a **test recipient/sender** address. That lets us
pinpoint it quickly (see *Opening a support ticket*).
