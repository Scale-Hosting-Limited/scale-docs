---
title: Setting up cron jobs
slug: setting-up-cron-jobs
description: Schedule scripts and tasks to run automatically on your web hosting.
---

A cron job runs a command or script automatically on a schedule — every few minutes,
nightly, weekly, whatever you need. They power background tasks like WordPress
scheduled posts, backups, and app maintenance. Here's how to set one up.

## What cron jobs are for

Common uses:

- **WordPress cron** — running scheduled posts, updates, and plugin tasks reliably.
- **Backups** — dumping a database or archiving files on a schedule (see *Backing up
  and restoring your site*).
- **App maintenance** — clearing caches, sending queued emails, syncing data.
- **Custom scripts** — anything you'd otherwise run by hand on a timer.

## Create a cron job

1. In your hosting control panel, open **Cron Jobs**.
2. Set the **schedule** — how often it runs.
3. Enter the **command** to run.
4. Save.

Many panels offer common presets ("once a day", "every 15 minutes") so you don't have
to write the schedule by hand.

## Understanding the schedule

Cron timing has five fields: **minute, hour, day-of-month, month, day-of-week**. A
`*` means "every". Examples:

- `0 3 * * *` → every day at 3:00am.
- `*/15 * * * *` → every 15 minutes.
- `0 0 * * 0` → midnight every Sunday.

Use a preset if the syntax is fiddly; get the schedule right or the job runs at the
wrong time (mind the server's timezone).

## Writing the command

The command is usually one of:

- **Run a PHP script:** call PHP with the script's full path, e.g.
  `php /home/you/public_html/script.php`.
- **Fetch a URL:** use `wget` or `curl` to hit a URL that triggers the task, e.g.
  `curl -s https://yourname.com/cron.php`.

Your app's docs will tell you which it expects. Use **full paths** — cron doesn't know
your shell's shortcuts.

## WordPress and cron

WordPress has its own "cron" that only fires when someone visits the site — unreliable
for a quiet site. For dependable scheduling:

1. Disable WordPress's built-in cron (a small edit to `wp-config.php`).
2. Add a **real cron job** that calls `wp-cron.php` on a schedule (e.g. every 15
   minutes).

This makes scheduled posts and tasks fire on time regardless of traffic.

## Test and monitor

- **Run it manually once** if your panel allows, to confirm it works.
- **Log the output** — redirect output to a file (`>> /path/cron.log 2>&1`) so you can
  see what happened.
- **Don't over-schedule** — running a heavy job every minute wastes resources; match
  the frequency to the need.

## Troubleshooting

- **Job didn't run:** check the schedule (and timezone), and that the command path is
  correct and absolute.
- **Runs but errors:** check the log output you redirected; run the same command over
  SSH/manually to see the error.
- **WordPress tasks still not firing:** confirm you disabled the built-in cron and the
  real cron calls `wp-cron.php`.
- **Not sure of the right command:** open a ticket with what you're trying to schedule
  (see *Opening a support ticket*).
