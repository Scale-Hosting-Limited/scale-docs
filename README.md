# Scale Hosting — Docs & Translations

User-facing documentation and interface translations for
[Scale Hosting](https://scalehosting.net).

## Help Center

The `help-center/` directory holds the help-center articles that are synced into
the panel's database. English lives in `help-center/en/`, organised by category;
translations mirror the same tree per language, and only **new-language**
help-center content is injected. See [`help-center/README.md`](help-center/README.md)
for the structure and file format.

## Translations

The `lang/` directory holds the interface translations for the client panel.
English (`lang/en/`) is the source; every other language is translated from it.

Contributions are welcome. If you'd like to improve a translation or add a
language, open a pull request against the relevant `lang/<code>/` files, or
translate through Crowdin (see `crowdin.yml` for the file mapping).

## Layout

- `lang/en/` — source strings (English).
- `lang/<code>/` — translations per language.
- `crowdin.yml` — Crowdin sync configuration.
