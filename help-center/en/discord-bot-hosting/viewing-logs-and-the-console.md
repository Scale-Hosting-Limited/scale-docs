---
title: Viewing logs and using the console
slug: viewing-logs-and-the-console
description: Read your bot's output, run commands, and debug from the panel console.
---

The **console** shows your bot's live output and lets you interact with the
service. It's the first place to look whenever something isn't working.

## What the console shows

Anything your bot prints — `console.log` in Node, `print`/logging in Python — appears
here in real time, along with startup messages, errors, and stack traces. A healthy
bot usually prints something like "Logged in as YourBot#1234" once it connects.

## Log usefully

Good logging makes debugging painless:

- Log a line on **ready** ("Logged in as …") so you can confirm it connected.
- Log **caught errors** with enough context to know what failed.
- **Don't log secrets** — never print your token or keys.
- Avoid spamming the console every event; it makes real errors hard to find.

## Reading errors

- **Node:** an unhandled error prints a stack trace; the top lines name the file
  and line. `UnhandledPromiseRejection` means an `await` threw without a `catch`.
- **Python:** a `Traceback` ends with the actual exception type and message — read
  the last line first, then work up.

## Restarting and stopping

Use the panel's **Restart** button after changing code, dependencies, or
variables — most changes need a restart to take effect. **Stop** takes it offline
until you start it again.

## Persisting logs

The console shows recent output; for a longer history, have your bot **write to a
log file** (e.g. a `logs/` folder) that you can download from the file manager.
Rotate or cap the file so it doesn't grow forever and fill your disk.

## Getting help

When you open a ticket, include the **console output around the error** — the last
20–30 lines are usually enough. A screenshot works, but copied text is easier for
us to read. Redact any secrets first (there shouldn't be any if you're using
environment variables).

## Troubleshooting

- **Console is empty after start:** your bot may have exited instantly — scroll up
  for an error, or see *Troubleshooting your bot*.
- **No "logged in" message:** it's not connecting — check the token and intents.
- **Errors scroll past too fast:** write to a log file and download it to read at
  your own pace.
