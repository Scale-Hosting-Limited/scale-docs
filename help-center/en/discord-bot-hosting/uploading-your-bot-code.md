---
title: Uploading your bot code
slug: uploading-your-bot-code
description: Get your bot project onto the server with the file manager, SFTP, or Git.
---

There are three ways to get your code onto your hosting. Pick whichever fits your
workflow.

## Option 1: file manager (quick)

1. Open your bot service and click **File Manager**.
2. Upload your project files into the main directory. If you have a `.zip`, upload
   it and **extract** it in place.
3. Make sure files sit in the **root**, not in a nested subfolder — the panel
   should see your `index.js`/`main.py` (and `package.json`/`requirements.txt`) at
   the top level, not inside `mybot/`.

Great for small bots and quick edits.

## Option 2: SFTP (best for larger projects)

Use FileZilla or similar with the SFTP details on your service page — faster and
better for many files. See *Connecting with SFTP* for the walkthrough. Drag your
project into the root.

## Option 3: Git (best for ongoing work)

If your bot is in a Git repo, pull it directly:

1. In the **console**, run `git clone <your-repo-url> .` into the root (the
   trailing `.` clones into the current folder).
2. To update later, `git pull`.

For private repos, use a deploy key or a token in the URL. Keep secrets out of the
repo — use environment variables (see *Environment variables and secrets*).

## What to upload — and what not to

**Do upload:** your source files, `package.json`/`requirements.txt` (or equivalent),
and any assets your bot needs.

**Don't upload:**
- **`node_modules/`** or a local Python `venv/` — install those on the server
  instead (see *Installing dependencies*); uploading them is slow and often breaks
  across environments.
- **Your token or `.env` with real secrets** — set those as environment variables
  on the server, not in files you upload.

A `.gitignore` that already excludes `node_modules`, `venv`, and `.env` keeps this
clean automatically.

## Next

Once the code is up: *Installing dependencies*, *Setting the startup command*, and
*Environment variables and secrets*. Then start the bot.

## Troubleshooting

- **Panel can't find your main file:** it's in a subfolder — move files to the
  root.
- **Upload of many small files is slow:** zip locally, upload the zip, extract on
  the server.
