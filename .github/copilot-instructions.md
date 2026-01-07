<!-- Copilot / AI agent instructions for HoustonCMS Jekyll site -->
# Copilot instructions — HoustonCMS (Jekyll)

Purpose: give an AI coding agent exactly the repo knowledge needed to be productive.

Big picture
- This repository is a Jekyll static site (see `_config.yml` for site settings and `Gemfile` for Jekyll version). The generated site lives in `_site/` — do not edit files there.
- Content sources: top-level Markdown/HTML and the `docs/`, `_posts/`, `assets/`, `_includes/`, and `_layouts/` directories. Data-driven menus live in `_data/` (e.g., `_data/menus.yml`).
- Templates: Liquid + YAML front matter. Docs pages use `layout: docs` (see `docs/launchpad.md` as an example).

How to run locally (developer workflow)
- Install Ruby dependencies: `bundle install` (Gemfile pins `jekyll ~> 4.4.1`).
- Serve locally: `bundle exec jekyll serve` (same as repository README). Use `bundle exec jekyll build` to create `_site`.
- Don’t modify `_site` — it’s generated output. When debugging templates, edit files in `_layouts/` and `_includes/` and re-run `bundle exec jekyll serve`.
- If Jekyll errors occur, run with `--trace` to get full stack traces.

Project conventions and patterns
- Pages and docs: use YAML front matter. Example: `docs/launchpad.md` uses `layout: docs` and contains code blocks and images under `assets/images/`.
- Posts: use `_posts/` with conventional filenames (YYYY-MM-DD-title.markdown).
- Assets: author CSS/JS in `assets/` (CSS in `assets/css/`, JS in `assets/js/`). SASS sources may be under `_sass/` (configured in `_config.yml`).
- Data-driven navigation: check `_data/menus.yml` for menu structure — agents should update that file to change site navigation, not `_includes` HTML directly.
- Plugins: site uses jekyll plugins listed in `_config.yml` / `Gemfile` (e.g., `jekyll-paginate`, `jekyll-sitemap`, `jekyll-feed`). Avoid adding new plugins without confirming compatibility with the pinned Jekyll version.

Integration points & external dependencies
- `Gemfile` → Ruby gems / Jekyll version. Use `bundle exec` for Jekyll commands.
- Third-party assets: `assets/js/silktide-consent-manager.js` and analytics placeholder `ganalytics` in `_config.yml`.
- The site’s `url` and `baseurl` are set in `_config.yml`; deployment scripts are not present in this repo — adjust `url`/`baseurl` for production builds if requested.

Editing guidance for AI agents
- Prefer edits to source Markdown/layouts/includes/assets; never change files under `_site/` (they will be overwritten).
- Preserve Liquid tags and YAML front matter formatting. When adding examples, follow existing site style (see `_layouts/default.html` and `_includes/cookies.html`).
- When changing site structure (new layouts, plugins, or major config changes), summarize the proposed change and ask the user before committing.

References (examples)
- Site config: `_config.yml`
- Build: `Gemfile` and `readme.md` (root) — run `bundle exec jekyll serve`
- Example docs: `docs/launchpad.md`
- Templates: `_layouts/`, `_includes/`
- Data-driven nav: `_data/menus.yml`

If anything is unclear, ask which environment should be targeted (local dev vs production) and whether you should update `Gemfile`/plugins before making breaking changes.
