---
title: Managing admins and players
slug: managing-admins-and-players
description: Grant admin access, kick or ban troublemakers, and keep your server friendly.
---

Running a good server is as much about people as it is about settings. Most games
give you tools to grant trusted admins, remove bad actors, and keep things fair.
Here's the general approach — check your game's guide for exact commands.

## Granting admin access

Admins can run privileged commands. Most games grant admin one of these ways:

- **An admin list file** — add a player's ID/username to a file like `admins.txt`,
  `adminlist`, or a config entry.
- **A console/RCON command** — run an "add admin" command from the panel console
  (see *Using the game panel console*).
- **A permissions plugin** — for finer control, a plugin defines roles and what each
  can do.

Grant admin **sparingly** — only to people you trust, since admins can change or
wipe a lot.

## Roles beyond full admin

For bigger communities, a permissions system lets you create tiers — moderators who
can kick and mute but not change settings, VIPs with perks, and so on. If your game
supports a permissions plugin, it's worth setting up rather than making everyone a
full admin.

## Kicking and banning

When someone's causing trouble:

- **Kick** removes them for now; they can rejoin. Good for a warning.
- **Ban** stops them coming back. Ban by their **account/ID** where possible, not
  just name or IP, since those change.
- **Temp-ban** (if supported) is a middle ground for a cooling-off period.

You can usually do this from the **console** or in-game as an admin. Keep a note of
why, in case they appeal.

## Whitelisting / allow-lists

To run a private or invite-only server, enable a **whitelist** so only approved
players can join. Add players' IDs to the allow-list and turn the setting on. This
is the most reliable way to keep a server private (see your game's specific guide,
and for Minecraft, *Operators, whitelist and permissions*).

## Dealing with griefing

- **Back up regularly** so you can roll back damage (see *Backing up and
  restoring*).
- Use **claim/protection plugins** where available to stop players wrecking each
  other's builds.
- **Log admin actions** if your tools allow, so you can see who did what.

## Keep it civil

- Post clear **rules** and pin them (in Discord, a MOTD, or a sign).
- Apply rules **consistently** — inconsistent moderation drives people away faster
  than strict rules.
- Give admins guidance on when to warn, kick, and ban so they act the same way.

## Troubleshooting

- **Admin commands not working:** confirm the player is actually on the admin list
  and the server was restarted/reloaded after editing it.
- **Ban not sticking:** ban by account ID, not name; some players rejoin under a new
  name.
- **Locked yourself out:** edit the admin file directly via **Files** or **SFTP** to
  restore your access.
