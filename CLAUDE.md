# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the GitHub Pages site for **qianwang-lab** (`qianwang-lab.github.io`) — the academic homepage of Dr. Qian Wang's **MIIL** (Medical Imaging and Informatics Laboratory) at ShanghaiTech University.

## Tech Stack

- **Jekyll** with the **Beautiful Jekyll** theme (`daattali/beautiful-jekyll` via `jekyll-remote-theme`)
- **GitHub Pages** native deployment (push to `main`, auto-build)
- Plugins: `jekyll-feed`, `jekyll-seo-tag`, `jekyll-sitemap`
- Custom CSS: gradient+vibrant style in `assets/css/style.css`

## Project Structure

```
_config.yml                          — Site config (theme, plugins, collections, site-css)
_data/navigation.yml                 — Main nav (Home, Team, Research, Publication)
_data/publications_journal.yml       — 141 journal paper entries (structured YAML)
_data/publications_conference.yml    — 118 conference paper entries (structured YAML)
_data/publications_misc.yml          — Misc publications (empty placeholder)
index.html                           — Homepage with hero, PI card, research cards, publications, CTA
_pages/                              — Static pages (permalink-based routing)
  team.md, research.md, publication.md, alumni.md    — Current pages
  *_old.md                                            — Retired pages from old site
_research/                           — Research topic sub-pages (Jekyll collection)
  medical-image-synthesis.md         — Example topic page
_posts/                              — Blog posts (5 research highlights from 2021–2022)
assets/css/style.css                 — Custom gradient+vibrant stylesheet
assets/images/uploads/               — Media files (WordPress migration paths)
assets/images/team/                  — Team member headshot photos (placeholder initials)
404.md                               — Custom 404 page
Gemfile                              — Ruby dependencies (github-pages gem + webrick)
```

## Key Conventions

- Pages live in `_pages/` with explicit `permalink:` in front matter (enabled via `include: ["_pages"]` in `_config.yml`)
- Navigation is defined in `_data/navigation.yml` using Beautiful Jekyll's `navbar-links` format
- Publications are structured YAML in `_data/publications_*.yml` (not inline Markdown lists)
- Research topic pages use the `_research/` Jekyll collection with `permalink: /research/:name/`
- Custom CSS loaded via `site-css` key in `_config.yml`
- Layouts: use `page` for static pages, `post` for blog. Do NOT use `home` layout (appends unwanted blog loop)
- Team member cards use placeholder initials when no photo is available

## Retired Pages

Old pages are renamed with `_old` suffix and moved to `/XXX-old/` permalinks. They can be deleted when no longer needed:
`biography_old.md`, `team_old.md`, `research_old.md`, `publication_old.md`, `journal-paper_old.md`, `conference-paper_old.md`, `alumni_old.md`, `recruitment_old.md`, `students-supervised_old.md`

## Build & Preview

```bash
export PATH="$HOME/.local/share/gem/ruby/3.2.0/bin:$PATH"
bundle install
bundle exec jekyll serve --host 0.0.0.0 --port 4000    # Preview at http://localhost:4000
```

**Important:** Restart `jekyll serve` after any `_config.yml` change — auto-regeneration does NOT hot-reload config.

## Repository

- **Remote**: `https://github.com/qianwang-lab/qianwang-lab.github.io.git`
- **Default branch**: `main`
- The repo follows the `<org>.github.io` pattern; GitHub Pages serves from `main`
