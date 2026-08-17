---
title: Spam filtering and blocklists
slug: spam-filtering-and-blocklists
description: Cut down incoming spam and handle false positives with allow/block lists.
---

Spam is a fact of email life, but you can reduce it a lot. This covers how filtering
works, how to tune it, and what to do when good mail gets caught or bad mail slips
through.

## How filtering works

Incoming mail is scored for spam-like signs — dodgy senders, known-bad content,
failed authentication, and reputation. Messages over a threshold are moved to
**Junk/Spam** or rejected. Most of this happens automatically; your job is mainly to
tune the edges.

## Tune your spam settings

In your email panel (or webmail settings) you can usually:

- **Adjust sensitivity** — stricter catches more spam but risks more false positives;
  looser does the reverse. Change it gradually.
- **Choose the action** — move to a Junk folder (safer) vs reject outright.
- **Set allow and block lists** (below).

Moving to Junk is usually safer than outright rejection, because you can rescue a
false positive.

## Allow lists (whitelist)

Add trusted senders or domains to an **allow list** so their mail always gets
through, even if it looks spammy. Good for:

- A newsletter or service that keeps landing in Junk.
- A colleague or client whose mail is being over-filtered.

## Block lists (blacklist)

Add persistent spammers to a **block list** so their mail is always rejected. Block
by **address** or, for a flood from one domain, the whole **domain**. Note that
determined spammers change addresses constantly, so blocking is a game of
whack-a-mole — filtering does most of the heavy lifting.

## Rescuing good mail from spam

If a legitimate message was filtered:

1. **Find it in the Junk/Spam folder** and mark it **Not spam** — this teaches the
   filter.
2. **Add the sender to your allow list** so it doesn't happen again.
3. If lots of good mail is caught, **lower the sensitivity** a notch.

## Reducing spam you receive

- **Don't post your address publicly** in plain text where scrapers find it.
- **Use aliases** for sign-ups so you can kill one that gets sold on (see *Aliases,
  forwarders, and catch-all*).
- **Reconsider a catch-all** — it invites spam to random addresses.
- **Never reply to or click "unsubscribe" in obvious spam** — it confirms your
  address is live.

## Troubleshooting

- **Too much spam getting through:** raise sensitivity a little and block repeat
  offenders; report/mark them as spam to train the filter.
- **Good mail keeps getting filtered:** mark **Not spam**, allow-list the sender, and
  ease the sensitivity.
- **Your own outgoing mail marked as spam by others:** that's a deliverability issue,
  not incoming filtering — see *Improving email deliverability* and *Setting up email
  DNS records*.
