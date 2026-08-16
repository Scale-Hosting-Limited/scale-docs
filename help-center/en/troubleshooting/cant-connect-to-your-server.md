---
title: You can't connect to your server
slug: cant-connect-to-your-server
description: Work out whether it's the server, the address, or your client — and fix each.
---

When you can't join, the problem is in one of three places: the server isn't
running, you're using the wrong address, or your client doesn't match. Here's how
to tell them apart.

## 1. Is the server actually online?

Open the panel. Is the status **green** and does the console show `Done`? If it's
off or crashed, that's your answer — start it, and if it won't stay up, see
*Your game server won't start*.

## 2. Are you using the right address?

Copy the address straight from the panel (top of the game panel). Common mistakes:

- Sharing `localhost` or `127.0.0.1` — those only mean "this computer." Always use
  the public address the panel shows.
- Missing the **port** when one is required (`address:25565`).
- On **Bedrock**, the port goes in its own field, not after a colon.
- A subdomain that hasn't finished pointing yet — give DNS a little time after
  setting it up.

## 3. Does your client match the server?

- **"Outdated client/server"** means your Minecraft version differs from the
  server's. Match them in the launcher or in the panel.
- **Modded:** a vanilla client can't join a modded server, and a different pack
  version will be refused. Everyone needs the same pack and version.
- **Java vs Bedrock:** they can't join each other without a bridge (Geyser).

## 4. Whitelist and bans

- **"You are not whitelisted"** — whitelisting is on and your name isn't listed.
  Add it (`whitelist add <name>`) or turn it off.
- **"You are banned"** — someone banned that name/IP. `pardon <name>` from the
  console.

## 5. It works for you but not for friends (or vice-versa)

- If it works locally but not for others, you're likely sharing the wrong address.
- If one player can't connect but everyone else can, it's their end — their
  Minecraft version, their network, or a firewall/VPN on their side. Have them try
  another network.

## 6. "Connection timed out" for everyone, server shows online

Give it a minute after a start — the server accepts connections only once the
console reaches `Done`. If it's been `Done` for a while and still nobody can join,
open a ticket with your address and we'll check the node and routing.

## Quick checklist

1. Server green + console shows `Done`? 
2. Public address (and port) copied exactly from the panel? 
3. Client version/pack matches the server? 
4. Not blocked by whitelist/ban? 

Ninety-nine times out of a hundred it's one of those four.
