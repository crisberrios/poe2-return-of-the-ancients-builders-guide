# PoE 2 0.5 — Return of the Ancients — Builder's Guide

Unofficial league-start research and per-ascendancy notes for *Path of Exile 2*
patch **0.5.0 "Return of the Ancients"** (Runes of Aldur league, 2026-05-29).

Bilingual (English + Español Latinoamérica). Served from GitHub Pages.

## Build

Site is built with [Zola](https://www.getzola.org/) (single static binary).

```sh
zola serve            # local dev with live reload
zola build            # one-shot build to ./public
```

CI builds and deploys on every push to `main` via `.github/workflows/deploy.yml`.

## Structure

```
config.toml           # Zola config (incl. [languages.es-LA])
content/
  _index.md           # EN homepage (summary ranking)
  _index.es-LA.md     # ES homepage
  <ascendancy>.md     # one per ascendancy, EN
  <ascendancy>.es-LA.md
templates/
  base.html           # shared layout + prominent language switcher
  index.html          # homepage (summary)
  page.html           # individual ascendancy pages
sass/main.scss        # PoE-inspired dark theme, no official assets
.github/workflows/
  deploy.yml          # GitHub Pages deployment
```

## Adding / editing content

Edit `content/<file>.md` for English and `content/<file>.es-LA.md` for Spanish.
Internal links between pages use Zola's `@/` resolver:

```markdown
[Titan notes](@/titan.md)            <!-- in EN files -->
[Notas del Titán](@/titan.es-LA.md)  <!-- in ES files -->
```

The page `<h1>` is rendered from the frontmatter `title` — don't add a manual
`# Heading` at the top of the body.

## Credits

Path of Exile and Path of Exile 2 are © Grinding Gear Games. This site uses
no official assets. The visual styling is custom CSS inspired by the genre
aesthetic only.
