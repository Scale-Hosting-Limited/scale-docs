---
title: Updating your bot
slug: updating-your-bot
description: Deploy new code and dependencies to your running bot safely.
---

Shipping an update is quick. The flow depends on how you got your code onto the
server in the first place.

## If you uploaded files (file manager / SFTP)

1. Upload the changed files, overwriting the old ones (SFTP is easiest for several
   files — see *Connecting with SFTP*).
2. If dependencies changed, update `package.json`/`requirements.txt` and reinstall
   (see *Installing dependencies*).
3. **Restart** the bot from the console.

## If you used Git

1. In the console, run `git pull` in your project root.
2. Reinstall dependencies if they changed (`npm install` / `pip install -r
   requirements.txt`), or just restart if auto-install is on.
3. **Restart** the bot.

This is the smoothest workflow for frequent updates — commit locally, push, then
`git pull` on the server.

## Updating slash commands

If you changed slash commands, remember Discord needs them **re-registered**:

- **Guild commands** update almost instantly — good for testing.
- **Global commands** can take up to an hour to propagate.

Run your command-registration script (or trigger it on startup) after deploying.

## Roll back if something breaks

- **Git:** `git checkout <previous-commit>` or `git revert`, then restart.
- **Files:** keep a copy of the previous version before overwriting, so you can put
  it back.
- Always check the console after a deploy — if the bot crash-loops on the new code,
  roll back and debug (see *Troubleshooting your bot*).

## Zero-surprise deploys

- Test locally first where you can.
- Deploy at a quiet time for your community.
- Watch the console through the restart until you see the "logged in" line.
- Keep secrets in environment variables so deploying code never risks leaking them.

## Troubleshooting

- **Old behaviour after deploy:** you didn't restart, or files landed in the wrong
  folder — confirm the path and restart.
- **New dependency missing:** you updated the manifest but didn't reinstall — run
  the install command and restart.
- **Slash command didn't change:** global commands are still propagating, or the
  registration script didn't run.
