---
title: Using a database with your bot
slug: using-a-database-with-your-bot
description: Give your bot persistent storage that survives restarts.
---

Anything your bot needs to remember between restarts — settings per server, user
data, economy balances — needs to live in **storage**, not just memory. When the
process restarts, in-memory state is gone.

## Options, simplest first

**SQLite (a file).** A single file on disk (`data.sqlite`). Zero setup, perfect for
small-to-medium bots. Use `better-sqlite3` (Node) or the built-in `sqlite3`
(Python). Keep the file in your project directory so it persists, and back it up.

**JSON file.** Fine for tiny amounts of config, but it doesn't handle concurrent
writes well and can corrupt if the process dies mid-write. Prefer SQLite once you
have real data.

**MySQL / MariaDB.** If your plan or account includes a database, create one and
connect with credentials as environment variables. Better for larger bots or when
you want to query data from elsewhere. See *Managing MySQL databases*.

**External / hosted DB.** You can also point your bot at a managed database
(Postgres, MongoDB, Redis, etc.) elsewhere — store the connection string as an
environment variable.

## Connecting securely

Put connection details in **environment variables**, never in code:

```
DB_HOST, DB_NAME, DB_USER, DB_PASSWORD    (or a single DATABASE_URL)
```

Read them with `process.env` / `os.environ` (see *Environment variables and
secrets*).

## Make it restart-safe

- **Persist to the DB**, don't keep the source of truth only in memory.
- **Load state on startup** — read what you need when the bot boots.
- Use the database's own atomic writes/transactions so a restart mid-operation
  can't corrupt data (another reason SQLite/MySQL beat a hand-written JSON file).

## Backups

Your data is only as safe as your backups:

- **SQLite/JSON:** download the file periodically from the file manager, or include
  it in your service backups.
- **MySQL:** export the database regularly (see *Managing MySQL databases*).

## Troubleshooting

- **Data resets on restart:** you're storing it in memory, or the SQLite file is in
  a temp location — keep it in your project folder and write to the DB.
- **"Database is locked" (SQLite):** concurrent writes — use a library with proper
  locking (`better-sqlite3`) and keep writes short.
- **Can't connect to MySQL:** wrong host/credentials in your env variables — verify
  against the Databases section.
