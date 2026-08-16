---
title: Connecting your email client
slug: connecting-your-email-client
description: Set up your new mailbox in Outlook, Apple Mail, Gmail, or your phone.
---

Once a mailbox exists, add it to any email app using the settings from your
service page.

## Settings you'll need

Your service page lists the exact values, but they look like this:

| Setting | Incoming (IMAP) | Outgoing (SMTP) |
|---------|-----------------|-----------------|
| Server | `mail.yourdomain.com` | `mail.yourdomain.com` |
| Port | 993 (SSL) | 465 (SSL) or 587 (STARTTLS) |
| Username | your full email address | your full email address |
| Password | your mailbox password | your mailbox password |

Use **IMAP** rather than POP3 so your mail stays in sync across devices.

## Add the account

1. In your mail app, choose **Add account → Other / IMAP**.
2. Enter your email address and password.
3. Enter the incoming and outgoing servers and ports above.
4. Save. The app will test the connection and start syncing.

## If sending fails

Most send problems are the outgoing port or SSL setting. Try 465 with SSL, or 587
with STARTTLS, and make sure the username is your **full** email address.
