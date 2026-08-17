---
title: Migrating email to us
slug: migrating-email-to-us
description: Move mailboxes from another provider without losing mail or downtime.
---

Switching your email to Scale Hosting doesn't mean losing your old mail. With a
little planning you can bring across your messages and folders and switch over with
no gap. Here's the safe way to do it.

## Plan before you switch

The golden rule: **don't remove the old service until the new one is fully working
and your mail is copied across.** Rushing the DNS change is what causes lost mail.

Make a list of:

- Every **mailbox** to move, and any **aliases/forwarders** (see *Aliases,
  forwarders, and catch-all*).
- Where your mail currently lives and how much there is.

## Step 1: Create your mailboxes here

Recreate each mailbox on our service **first**, so there's somewhere for mail to land
when you switch (see *Creating a mailbox*). Set the same addresses you use now.

## Step 2: Copy your existing mail across

You have a few options:

- **IMAP migration tool** — if offered, point it at your old provider (host,
  username, password) and it copies mail and folders into the new mailbox. Easiest for
  bulk moves.
- **Drag-and-drop in a mail client** — add **both** accounts (old and new) in an
  IMAP client, then drag folders/messages from old to new. Reliable for smaller
  mailboxes.
- **Export/import** — export from the old provider and import here, if both support
  it.

Do this **before** changing DNS, while both mailboxes still receive.

## Step 3: Update DNS to point mail at us

Once mail is copied and the new mailboxes work:

1. Change your **MX record** to our mail host, and set **SPF/DKIM/DMARC** (see
   *Setting up email DNS records*).
2. **Remove the old MX** so mail stops going to the previous provider.
3. Allow time for DNS to propagate — during which a little mail may still hit the old
   server, so keep it open briefly.

## Step 4: Reconfigure your devices

Update the settings in your phone and desktop mail apps to our incoming/outgoing
servers (see *Connecting your email client*). Test sending and receiving on each
device.

## Step 5: Keep the old account open (briefly)

Don't cancel the old email straight away. Leave it open for a short overlap to catch
any stragglers during propagation. Once you're confident nothing new is arriving
there, you can close it.

## Verify the move

- **Send and receive** test messages both ways (see *Email not sending or
  receiving*).
- **Check folders** came across intact.
- **Confirm SPF/DKIM pass** with a mail-tester so you don't land in spam (see
  *Improving email deliverability*).

## Troubleshooting

- **Missing mail after the move:** check the old account and copy across anything that
  arrived during the switch; this is why you keep it open.
- **New mail in spam:** set SPF/DKIM/DMARC correctly.
- **Client errors:** recheck server, port, and password (see *Connecting your email
  client*).
- **Stuck on the migration tool:** open a ticket with the details and we'll help (see
  *Opening a support ticket*).
