# Project conventions for Claude

## Commit messages
- **Never** add a `Co-Authored-By: Claude ...` trailer (or any other Claude attribution line) to commit messages.

## Site build

This is a Zola static site. Useful commands:

- `zola serve` — local dev with live reload
- `zola build` — one-shot build to `./public`

CI deploys on push to `main` via `.github/workflows/deploy.yml`.

## Content layout

- `content/<file>.md` is the English version.
- `content/<file>.es-LA.md` is the Spanish (LatAm) version.
- Keep both in sync when editing — every content change should update both
  language versions unless the content is language-specific (e.g. the
  glossary at `content/glosario.es-LA.md`).
- Internal links use Zola's `@/` resolver. In `*.md` files use `@/foo.md`;
  in `*.es-LA.md` files use `@/foo.es-LA.md`.
- The page `<h1>` comes from the frontmatter `title`; don't add a manual
  `# Heading` at the top of the body.

## Versioning

- Releases are tagged `vX.Y` (annotated tags).
- Maintain the changelog section at the bottom of `content/_index.md` and
  `content/_index.es-LA.md`. Add a new `### vX.Y (YYYY-MM-DD)` block with
  short bullet points each time a tag is cut.
