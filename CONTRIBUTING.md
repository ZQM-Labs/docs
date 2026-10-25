# Contributing to ZQM Labs Docs

Source for [docs.zqmlabs.com](https://docs.zqmlabs.com/) — the ZQM Labs
documentation hub: how to play, the host handbook, and the front door to
every ZQM Labs doc site. This file covers the contribution path for this
repo only: edit Markdown, check the navigation, preview locally, and open
a pull request against `main`.

## What lives here

- `mkdocs.yml` — site configuration and the full navigation tree.
- `docs/` — the site pages: `index.md`, `how-to-play.md`, `faq.md`,
  `contact.md`, `doc-sites.md`, and `hosting/` (the host handbook).
- `docs/overrides/main.html` — the Material theme override for Open Graph
  / Twitter-card meta. `docs/_headers` ships with the built site.

## How to contribute

1. Fork the repo, or branch from `main` if you have write access, and
   make your edit in the Markdown file that owns the topic — don't
   duplicate a page's content into a second page.
2. If you add, rename, or move a page, update the `nav:` section in
   `mkdocs.yml` in the same change. Every nav entry must point at a page
   that actually exists under `docs/`; a nav entry without its file (or
   a file without its nav entry) is a broken change.
3. If your change adds or renames a ZQM Labs doc site, update
   `docs/doc-sites.md` too — it is the index of all doc sites, and it
   goes stale silently when a site ships without a row here.
4. Keep the facts consistent with the rest of the handbook: kit prices,
   the edition window, and the contact address appear on several pages,
   so check the other pages that state the same fact before changing one
   of them. Questions the docs don't answer belong on `docs/contact.md`,
   not in a new page.
5. Open a pull request against `main` describing what changed and which
   pages you checked.

## Check before you open the PR

This repo has no CI workflow and no test suite, so these checks run
locally, by the author:

```sh
mkdocs serve    # preview with live reload, click through the changed pages
mkdocs build    # the build must succeed with no warnings about missing nav targets
```

Confirm the built output still contains the pages you touched and that
internal links on the changed pages resolve to headings that exist.

## Deploy note

This repo contains no deploy script and no CI workflow, so the step that
takes a built site to docs.zqmlabs.com is not documented here. Do not
assume a git-based Pages integration; confirm the deploy route with the
maintainer before publishing. The `docs/_headers` file is part of the
site source — verify it lands in the deployed output rather than
assuming it does.

## License

MIT — see `LICENSE`. By contributing you agree your changes are covered
by the same license.
