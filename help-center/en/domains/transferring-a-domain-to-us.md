---
title: Transferring a domain to us
slug: transferring-a-domain-to-us
description: Move a domain from another registrar to Scale Hosting without downtime.
---

Already own a domain elsewhere? You can transfer it to us so everything lives in
one account. A transfer doesn't interrupt your website or email as long as you
follow the steps — your existing DNS keeps working throughout.

## Before you start

At your **current** registrar, make sure:

1. The domain is **unlocked** (turn off "registrar lock" / "transfer lock").
2. You have the **authorisation code** (also called EPP code, auth code, or
   transfer key). You request this from the current registrar.
3. **WHOIS privacy is off** temporarily, if it blocks the auth email — you can turn
   it back on afterwards.
4. The domain is **not within 60 days** of being registered or a previous transfer
   — registry rules block transfers during that window.
5. Your **admin/registrant email is reachable**, as the approval usually goes there.

## Start the transfer

1. In your panel go to **Domains → Transfer**.
2. Enter the domain and the **authorisation code**.
3. Pay the transfer fee. For most endings this **adds a year** to your
   registration, so you're not losing time.
4. Approve the transfer when prompted — you may get an email from the current or
   new registrar to confirm.

## How long it takes

Most transfers complete in **a few days**. The delay is set by registry rules and
how quickly the old registrar releases the domain — you can often speed it up by
**approving/accepting** the transfer at the losing registrar rather than waiting
for it to time out.

## Keep your services running

A transfer moves *who manages the domain*, not its DNS settings — but to be safe:

- **Copy your DNS records** before you start (note your A, CNAME, MX, TXT records).
- After the transfer, check your DNS in **Domains → Manage** and re-add anything
  missing (see *Managing DNS records*).
- If your website or email points elsewhere, set the records to match **before**
  changing nameservers.

## After it completes

- Turn **auto-renew** back on so it can't lapse.
- Re-enable **domain privacy** if you want it (see *Domain privacy and WHOIS*).
- Confirm the registrant details are correct (see *Updating your profile and
  contact details*).

## If a transfer fails

Common causes: the domain was locked, the auth code was wrong or expired, it was
inside the 60-day window, or the approval email wasn't actioned. Fix the cause and
start again — you won't be charged twice for a failed attempt. Still stuck? Open a
ticket with the domain name and we'll look into it.
