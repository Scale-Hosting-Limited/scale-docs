---
title: Reading server logs
slug: reading-server-logs
description: Find, read, and make sense of logs to diagnose almost any problem.
---

When something goes wrong, the logs almost always say why. Learning to find and read
them turns "it's broken and I don't know why" into "here's the exact error" — which
you can fix yourself or hand us for a fast answer.

## Where logs live

- **Live console** — your game or app panel shows real-time output while the service
  runs (see *Using the game panel console*). Best for watching a startup or a crash
  as it happens.
- **Log files** — most software also writes to files, often under a `logs/` folder,
  which you can open in **Files** or download over SFTP (see *Connecting with
  SFTP*). Common names: `latest.log`, `error.log`, `debug.log`.
- **Web/app logs** — web hosting keeps error logs in the control panel or a `logs`
  directory.

The live console shows *now*; log files keep the *history*, including what scrolled
past too fast to read.

## How to read them

1. **Find the moment it failed** — scroll to when the server stopped or the error
   appeared.
2. **Look for the level markers** — `ERROR`, `SEVERE`, `FATAL`, `WARN`. The
   `ERROR`/`FATAL` lines are the real problem; warnings are often harmless.
3. **Read the first error, not the last.** A failure often cascades — the **first**
   error is usually the cause; the ones after are side effects.
4. **Read just above the crash** — the lines right before a crash usually name what
   triggered it.

## Reading a stack trace

A stack trace is the indented block after an error. You don't need to understand all
of it:

- The **top line** names the error type and message.
- Look for a **file, mod, or plugin name** you recognise — that's usually the
  culprit.
- "Caused by:" lines point at the **root** cause deeper down.

## Common things logs reveal

- **A specific mod/plugin failing** — named right in the error (see *Server won't
  start*).
- **Port already in use** — the service didn't shut down cleanly; restart it.
- **Out of memory** — needs more RAM or is overloaded (see *Out of memory and
  resource limits*).
- **Missing file or dependency** — something referenced isn't there.
- **Permission or path errors** — a file can't be read or written.

## When you open a ticket

Copy the **relevant lines** — the error and a bit of context around it — into your
ticket. Don't paste thousands of lines; the error plus the ~20 lines around it tells
us far more (see *Opening a support ticket*). "It won't start" is slow to solve; the
actual error line is fast.

## Tips

- **Reproduce and watch** — restart and read from the top if you're chasing a
  startup error.
- **Note the timestamp** so you can match it to when the problem happened.
- **Don't ignore repeated warnings** — a warning that appears constantly can be the
  early sign of a bigger issue.
