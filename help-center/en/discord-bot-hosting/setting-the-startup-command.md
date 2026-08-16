---
title: Setting the startup command
slug: setting-the-startup-command
description: Tell the panel how to run your bot — the main file and run command per language.
---

The **startup command** is how the panel launches your bot. Set it on the
service's **Startup**/**Settings** tab so pressing Start runs the right thing.

## Node.js (discord.js)

Point it at your entry file:

```
node index.js
```

If your `package.json` has a start script, you can use `npm start`. Make sure the
**main file name matches** what you uploaded (`index.js`, `bot.js`, `src/index.js`,
etc.). For TypeScript, build first (`npm run build`) and run the compiled output
(`node dist/index.js`).

## Python (discord.py / Pycord / nextcord)

```
python main.py
```

Use the filename of your entry script. On some images `python3` is the command —
if `python` isn't found, try `python3 main.py`.

## Java (JDA)

Run your built jar:

```
java -jar yourbot.jar
```

Build it locally (or with a build step) and upload the jar, or set a build command
if your image supports one.

## Other runtimes

Go, Rust, and others follow the same idea: build if needed, then run the binary or
entry file. See *Supported languages and runtimes*.

## Environment / version

- Many images let you pick a **runtime version** (Node 18/20/22, Python 3.11/3.12)
  on the same tab — match it to what your bot needs.
- Some panels have a **"main file"** field separate from the command — set both
  consistently.

## Auto-install on start

Some images run an **install step** before your command (e.g. `npm install` or
`pip install -r requirements.txt`) each boot. If yours does, you may not need to
install manually — but see *Installing dependencies* either way.

## Troubleshooting

- **"Cannot find module" / "No such file":** the startup command points at the
  wrong file, or files are in a subfolder. Fix the path or move files to the root.
- **Command not found (`node`/`python`):** wrong runtime image selected, or use
  `python3`.
- **Starts then exits immediately:** usually a crash on boot — check the console
  and *Troubleshooting your bot*.
