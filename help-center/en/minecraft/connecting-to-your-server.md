---
title: Connecting to your Minecraft server
slug: connecting-to-your-server
description: Find your server address and join from Java or Bedrock, with fixes for the usual connection errors.
---

Once your server is online, joining takes a few seconds. This guide covers where
to find your address, how to connect from both editions, and what to do when it
won't let you in.

## Find your server address

Open your service in the panel. The **address** is shown at the top of the game
panel — it looks like an IP and port (`123.45.67.89:25565`) or a friendly domain
(`play.yourserver.net`). If your plan includes a dedicated port you may only need
the IP; otherwise include the port after a colon.

If you've set up a subdomain (see *Setting up a custom address*), use that — it's
easier for players to remember and it keeps working even if the underlying IP
changes.

## Join from Java Edition

1. Launch Minecraft: Java Edition (make sure the launcher version **matches your
   server version** — a 1.20.1 server won't accept a 1.21 client).
2. Click **Multiplayer → Add Server**.
3. Put anything in the name field, paste your address into **Server Address**, and
   click **Done**.
4. Select the server and click **Join Server**.

## Join from Bedrock Edition

Bedrock (Windows 10/11, mobile, console) connects a little differently:

1. Go to **Play → Servers → Add Server**.
2. Enter a name, the **server address**, and the **port** in its own field.
3. Save and join.

Note that Java and Bedrock are not cross-compatible by default. If you want both
editions to join the same server, you'll need a server type like **Paper with
Geyser/Floodgate** — see *Installing plugins and mods*.

## Sharing with friends

Give your players the same address you use. They don't need an account with us —
only a copy of Minecraft on the right version. If you're whitelisting, remember to
add their usernames first (see *Operators, whitelist and permissions*).

## Common connection problems

**"Can't connect to server" / connection timed out**
- The server may be offline or still starting. Check the panel — the console
  should show `Done` and the status should be green. Press **Start** if it's off.
- Double-check the address and port for typos.

**"Outdated client" or "Outdated server"**
- Your Minecraft version doesn't match the server. Change your client version in
  the launcher, or change the server version in the panel to match.

**"Connection refused"**
- The server isn't listening yet (still booting) or has crashed on start. Open the
  console and look for errors — see *Server won't start* in Troubleshooting.

**You can join but others can't (or vice-versa)**
- If it works for you on the local network but not for friends, you're likely
  sharing the wrong address — always share the public address shown in the panel,
  not a `localhost` or `127.0.0.1` address.

**"You are not whitelisted on this server"**
- Whitelisting is on and your username isn't added. Add it from the console with
  `whitelist add <name>`, or turn the whitelist off.

If none of these help, open a support ticket with your server address and a
screenshot of the exact error and we'll take a look.
