---
title: Environment variables and secrets
slug: environment-variables-and-secrets
description: Store your bot token and other secrets safely, out of your code.
---

Your bot token, API keys, and database passwords are **secrets**. Never hard-code
them or commit them to Git — store them as **environment variables** on the server
and read them in your code.

## Setting variables

On your service's **Startup**/**Variables** tab, add each secret as a key/value:

```
DISCORD_TOKEN = your-token-here
DB_PASSWORD   = ...
API_KEY       = ...
```

These are injected into your bot's environment when it runs, and aren't part of
your uploaded files.

## Reading them in code

**Node.js:**
```js
const token = process.env.DISCORD_TOKEN;
client.login(token);
```

**Python:**
```python
import os
token = os.environ["DISCORD_TOKEN"]
bot.run(token)
```

## Using a .env file

If your project uses a `.env` file locally (with `dotenv` or `python-dotenv`), you
can create one on the server via the file manager — but **never upload your real
`.env` from Git**, and keep `.env` in `.gitignore`. Setting the values on the
Variables tab is cleaner and keeps them off the filesystem entirely.

## If a token leaks

If your token is ever exposed (committed to a public repo, pasted in a channel),
**reset it immediately** in the Discord Developer Portal (Bot → Reset Token) and
update the `DISCORD_TOKEN` variable. The old token dies the instant you reset.
Discord also auto-invalidates tokens it detects in public repos.

## Good practice

- One variable per secret; descriptive names.
- Never log secrets (don't `console.log(process.env.DISCORD_TOKEN)`).
- Rotate keys periodically and whenever someone with access leaves your team.
- Keep secrets out of screenshots when you ask for help.

## Troubleshooting

- **"Invalid token" on start:** the variable name in your code doesn't match the
  one you set, or it wasn't saved — check spelling and restart.
- **Works locally, fails hosted:** you were reading from a local `.env` that isn't
  on the server — set the variables on the Variables tab.
