---
title: Installing dependencies
slug: installing-dependencies
description: Install your bot's packages with npm, pip, or your language's tooling.
---

Your bot relies on libraries (discord.js, discord.py, etc.). Install them **on the
server** rather than uploading them, so they're built for the right environment.

## Node.js

From the **console**, in your project root:

```
npm install
```

This reads `package.json` and installs into `node_modules`. If you have a
`package-lock.json`, `npm ci` is faster and reproducible. Don't upload
`node_modules` yourself — install it here.

## Python

```
pip install -r requirements.txt
```

Keep a `requirements.txt` listing your packages (`discord.py`, etc.). If `pip`
isn't found, try `pip3`. Some images use a virtual environment automatically; if
yours doesn't, installing to the user site is fine for a bot.

## Run it automatically on start

Many bot images run an install step **before** your startup command on every boot
(for example `npm install` or `pip install -r requirements.txt`). If yours does,
new dependencies install themselves whenever you restart — you just keep
`package.json`/`requirements.txt` up to date. Check your service's Startup tab for
an install/build field.

## Adding a new dependency later

1. Add it to `package.json` (or `requirements.txt`) — locally or via the file
   manager.
2. Run the install command again in the console (or just restart if auto-install
   is on).
3. Restart the bot so it picks up the new library.

## Tips

- **Pin versions** in your manifest so a surprise update doesn't break your bot.
- Keep `node_modules`/`venv` out of Git and out of your uploads — regenerate them
  on the server.
- If installs are slow or run out of memory on a big dependency tree, a larger plan
  helps, but most bots install fine on entry plans.

## Troubleshooting

- **"Cannot find module 'discord.js'":** dependencies aren't installed — run
  `npm install` and restart.
- **`ModuleNotFoundError`:** the package isn't in `requirements.txt` or pip didn't
  run — install it and restart.
- **Install fails:** check the error in the console; a native package may need a
  build tool the image lacks — ask us if you're unsure.
