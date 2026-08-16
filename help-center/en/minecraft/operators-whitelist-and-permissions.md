---
title: Operators, whitelist, and permissions
slug: operators-whitelist-and-permissions
description: Give trusted players admin rights, restrict who can join, and manage permissions with a plugin.
---

Controlling who can join and who can run commands is how you keep a server safe
and running the way you want. There are three layers: operators, the whitelist,
and (optionally) a permissions plugin.

## Operators (ops)

An operator has full admin rights — they can run any command, kick/ban players,
change gamemode, and more. Grant op sparingly and only to people you trust.

From the **console** (in the panel):

```
op PlayerName
deop PlayerName
```

You can also edit `ops.json`, but the console is easier and takes effect
immediately. Set the default op level with `op-permission-level` in
`server.properties` (4 = full).

## The whitelist

A whitelist restricts joining to approved usernames — the simplest way to keep a
private server private.

Turn it on in `server.properties` (`white-list=true`) or from the console, then
manage names:

```
whitelist on
whitelist add PlayerName
whitelist remove PlayerName
whitelist list
whitelist reload
```

Ops can always join even when whitelisted. On Bedrock/Geyser setups, add the
Bedrock name in the format your Floodgate prefix expects.

## Banning and kicking

```
kick PlayerName reason
ban PlayerName reason
ban-ip 1.2.3.4
pardon PlayerName        (unban)
banlist
```

## Fine-grained permissions with a plugin

Ops are all-or-nothing. For roles like "moderator can kick but not change
gamemode," or per-rank perks, use a permissions plugin — **LuckPerms** is the
standard choice on Paper/Spigot.

1. Install LuckPerms (see *Installing plugins and mods*) and restart.
2. Create groups and assign permissions:

```
lp creategroup moderator
lp group moderator permission set minecraft.command.kick true
lp user PlayerName parent add moderator
```

3. Give groups a ladder (`default` → `moderator` → `admin`) and add each
   plugin's permission nodes as you go — every plugin documents its own nodes.

With a permissions plugin you can usually stop handing out op entirely, which is
much safer: a compromised op account can wreck a server, while a scoped role
can't.

## Good practice

- Keep the op list short; use LuckPerms for everything else.
- Turn on the whitelist while you're setting up, even if you open it later.
- Never share your panel login — that's separate from in-game op and controls the
  whole server.
