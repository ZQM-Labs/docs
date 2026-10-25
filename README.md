# ZQM Labs Docs

Source for [docs.zqmlabs.com](https://docs.zqmlabs.com/) — practical **ZQM Labs game documentation** for playing Wisp's Lost Lanterns, hosting a community scavenger hunt, preparing an event, handling day-of problems, and finding every ZQM Labs documentation site.

## What is in this repo

- `mkdocs.yml` — site configuration: site name and URL, the Material theme
  with `docs/overrides` as the custom directory, and the full navigation.
- `docs/` — the site pages in Markdown:
  - `index.md` — home page
  - `how-to-play.md`, `faq.md`, `contact.md`, `doc-sites.md` (the index of
    all ZQM Labs doc sites)
  - `hosting/` — the host handbook: hosting a game, choosing a tier,
    before the event, running the event, day-of troubleshooting, safety
    and supervision, and after the event
  - `overrides/main.html` — a Material theme override for Open Graph /
    Twitter-card meta
  - `_headers` — headers shipped with the built site

## Build and preview

This is a MkDocs site using the Material theme (see `mkdocs.yml`).

Preview locally with live reload:

```sh
mkdocs serve
```

Build the static site (output goes to the standard MkDocs `site/`
directory):

```sh
mkdocs build
```

Check the navigation in `mkdocs.yml` after adding or renaming a page: every
nav entry must point at a page that actually exists under `docs/`.

## Deploy

This repo contains no deploy script and no CI workflow, so the step that
takes a built site to docs.zqmlabs.com is not documented here. Confirm the
deploy route before publishing; do not assume a git-based Pages
integration. The `docs/_headers` file is part of the site source — verify
it lands in the deployed output, rather than assuming it does.

## Contact

Questions about hosting or the docs: see `docs/contact.md` in this repo,
or write to zqmcomputing@gmail.com.

## License

MIT — see `LICENSE`.
