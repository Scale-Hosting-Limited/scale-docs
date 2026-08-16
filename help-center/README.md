# Help Center

Source content for the Scale Hosting help center. This is synced to the database
by the injection pipeline; **only new-language help-center content is injected**.

## Layout

```
help-center/
  en/                     ← source language (English)
    <category>/
      _category.md        ← category metadata (name, slug, description)
      <article>.md        ← one article per file
  <lang>/                 ← translations, same tree as en/ (added by the pipeline)
```

English (`en/`) is the source of truth. Other languages mirror the same folders
and filenames; the injector treats a `<lang>/` tree that isn't yet in the database
as new-language content to insert.

## File format

**`_category.md`** — front-matter only:

```markdown
---
name: Minecraft
slug: minecraft
description: Guides for running and managing your Minecraft server.
---
```

**Article** — front-matter + Markdown body (maps to the Helpcenter `Article`
model: `title`, `slug`, `description`, `content`):

```markdown
---
title: Setting up your Minecraft server
slug: setting-up-your-minecraft-server
description: Create your server, pick a version, and start it for the first time.
---

Article body in Markdown…
```

## Categories

| Slug | Category |
|------|----------|
| `getting-started` | Getting Started |
| `minecraft` | Minecraft |
| `discord-bot` | Discord Bot |
| `web-hosting` | Web Hosting |
| `email-hosting` | Email Hosting |
| `billing` | Billing & Payments |
| `account-security` | Account & Security |

## Adding content

- **New article:** add `en/<category>/<slug>.md` with the front-matter above.
- **New category:** create `en/<new-slug>/_category.md`, then add articles.
- **Translations:** the pipeline manages `<lang>/` trees; keep `en/` authoritative.
