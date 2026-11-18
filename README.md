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

Source: this repo (`mkdocs.yml`, `docs/`). The live site is Cloudflare Pages
project `docs` (`docs-8ym.pages.dev`), custom domain `docs.zqmlabs.com` —
**direct upload, no Git source and no native Pages Git build**. CI
(`.github/workflows/docs-ci.yml`) builds with `mkdocs build --strict` on the
self-hosted Linux runners and verifies `site/index.html`; it does not deploy.

Repeatable route:

1. Build: `mkdocs build --strict` (output goes to `site/`).
2. Upload `site/` with `wrangler pages deploy site --project-name=docs`
   (needs a token with Pages:Edit — currently unverified) or by drag-and-drop
   in the Cloudflare dashboard (Pages → `docs` → Create deployment).
3. Verify live: fetch `https://docs.zqmlabs.com/` (200), confirm the changed
   pages are present, and confirm `docs/_headers` took effect (live must
   return `X-Frame-Options: DENY`).

Known state (2026-11-18): last deployed 2026-10-24T16:35Z; the repo has since
been pushed (last push 2026-11-18), so live is stale — the Oct 25–26 Lantern
Keeper sections are not live, and `_headers` is not taking effect live (no
`X-Frame-Options` header). A re-deploy is owed. The original Oct 24 upload
mechanism (wrangler vs dashboard) is unconfirmed.

## Contact

Questions about hosting or the docs: see `docs/contact.md` in this repo,
or write to zqmcomputing@gmail.com.

## License

MIT — see `LICENSE`.
