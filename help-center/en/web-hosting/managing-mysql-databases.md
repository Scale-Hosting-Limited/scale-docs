---
title: Managing MySQL databases
slug: managing-mysql-databases
description: Create databases and users, and manage them with phpMyAdmin.
---

Most web apps (WordPress, forums, custom sites) need a database. Your control
panel manages these under **Databases** (MySQL/MariaDB).

## Create a database and user

1. Open **Databases** in your control panel.
2. **Create a database** — note the full name (it's often prefixed with your
   account, like `user_myapp`).
3. **Create a database user** with a strong password.
4. **Assign the user to the database** with the privileges it needs (for most
   apps, all privileges on that one database).

Keep the name, user, and password somewhere safe — your app's config needs all
three.

## Connect your app

In your app's config (for WordPress, `wp-config.php`), set:

- **Database name** — the full name from above.
- **Username / password** — the DB user you created.
- **Host** — usually `localhost` (some setups use a specific hostname the panel
  shows — use that if given).

## phpMyAdmin

phpMyAdmin is a web tool for looking inside a database — browsing tables, running
SQL, and importing/exporting.

- **Export (backup):** select the database → **Export** → Go. Download the `.sql`
  file before any risky change.
- **Import (restore):** select the database → **Import** → choose your `.sql`
  file → Go. For large files, import over the command line or ask us.
- **Edit data:** browse a table to view/edit rows directly — handy for fixing a
  WordPress site URL, for example.

## Good practice

- **One database per app.** Don't share a single database between unrelated apps.
- **Least privilege.** An app only needs rights on its own database.
- **Back up before migrations/updates.** An export takes seconds and saves hours.
- **Strong, unique DB passwords** — they're a credential like any other.

## Troubleshooting

- **"Access denied for user":** wrong username/password, or the user isn't assigned
  to that database. Re-check the assignment and privileges.
- **"Unknown database":** the name in your config doesn't match — remember the
  account prefix.
- **App connects locally but not after moving hosts:** update the host, name, and
  credentials in the config to the new server's values.
- **Import fails on size:** the file is over the upload limit — compress it, split
  it, or open a ticket and we can import it for you.
