---
title: Choosing a PHP version
slug: choosing-a-php-version
description: Pick the right PHP version for your site and change it safely.
---

PHP powers WordPress and most other popular web apps, and the version you run affects
speed, security, and compatibility. This explains how to choose one and switch
without breaking your site.

## Why the PHP version matters

- **Security** — older PHP versions stop getting security updates. Running an
  unsupported version is a real risk.
- **Speed** — newer PHP is significantly faster, which means quicker page loads.
- **Compatibility** — your app, theme, and plugins must support the version you pick.
  Too new *or* too old can cause errors.

The goal: run a **currently supported** version that your software is compatible with.

## Check what your app needs

Before changing anything, find your app's supported PHP versions:

- **WordPress** publishes a recommended PHP version — aim for that or the latest it
  supports.
- **Other apps/frameworks** list their requirements in their docs.
- **Plugins/extensions** can lag behind — one incompatible plugin can break on a new
  version.

Match the version to the **whole stack**, not just the core app.

## Change your PHP version

1. In your hosting control panel, find **Select PHP Version** (or **PHP Settings**).
2. Choose the version you want.
3. Save/apply. It usually takes effect within moments.
4. **Test your site** thoroughly afterwards (below).

## Test after switching

A version change can surface incompatibilities, so check:

- The **homepage and key pages** load without errors.
- The **admin area** (e.g. WordPress dashboard) works.
- **Forms, logins, and checkout** function.
- The **error log** is clean (see *Reading server logs*).

If something breaks, switch back to the previous version while you sort out the
incompatible component.

## PHP extensions and settings

Beyond the version, you can often toggle **PHP extensions** (like `imagick`, `gd`,
`mysqli`) and adjust settings such as **memory limit**, **max upload size**, and
**execution time**. Some apps need specific extensions on, or a higher upload limit
for big media — enable those in the same PHP settings area.

## Upgrade steadily

When moving to a much newer PHP version:

1. **Back up first** (see *Backing up and restoring your site*).
2. **Update your app, theme, and plugins** to current versions — they're far more
   likely to support new PHP.
3. **Then switch** the PHP version and test.

Jumping several versions at once on out-of-date software is the usual cause of a
white screen.

## Troubleshooting

- **White screen / 500 error after switching:** revert to the previous version, then
  update your plugins/theme before trying again; check the error log.
- **A plugin breaks on the new version:** update or replace it, or stay on the older
  version until it's compatible.
- **"Missing extension" errors:** enable the required PHP extension in the PHP
  settings.
- **Still stuck:** open a ticket with the exact error and your current PHP version
  (see *Opening a support ticket*).
