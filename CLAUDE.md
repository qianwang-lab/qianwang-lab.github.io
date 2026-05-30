# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the GitHub Pages site for **qianwang-lab** (`qianwang-lab.github.io`) — the academic homepage of Dr. Qian Wang's research group, "Exploring in Medical Imaging and Informatics."

## Tech Stack

- **Jekyll** with the **Minimal Mistakes** theme (via `jekyll-remote-theme`)
- **GitHub Pages** native deployment (push to `main`, auto-build)
- Plugins: `jekyll-include-cache`, `jekyll-feed`, `jekyll-seo-tag`, `jekyll-sitemap`

## Project Structure

```
_config.yml          — Site config (theme, plugins, collections, defaults)
_data/navigation.yml — Main nav menu (Biography, Research, Publication, Team, Recruitment)
index.html           — Homepage with hero + recent research highlights
_pages/              — All static pages (permalink-based routing)
  biography.md, research.md, publication.md, journal-paper.md,
  conference-paper.md, team.md, alumni.md, students-supervised.md, recruitment.md
_posts/              — Blog posts (research highlights, 5 posts from 2021–2022)
assets/images/uploads/ — Media files migrated from WordPress wp-content/uploads/
404.md               — Custom 404 page
robots.txt           — Allow all with sitemap reference
Gemfile              — Ruby dependencies for GitHub Pages
```

## Key Conventions

- Pages live in `_pages/` with explicit `permalink:` in front matter (enabled via `include: ["_pages"]` in `_config.yml`)
- Navigation is defined in `_data/navigation.yml`, NOT in `_config.yml` (Minimal Mistakes reads from the data file)
- Publication lists (`journal-paper.md`, `conference-paper.md`) are numbered Markdown lists with `**[title](url)**` and `*journal*` formatting
- Images use `/assets/images/uploads/YYYY/MM/filename` paths (migrated from WordPress `wp-content/uploads/`)

## Build & Preview

```bash
bundle install
bundle exec jekyll serve    # Preview at http://localhost:4000
```

Ruby is not installed on the current development machine — to preview, either install Ruby locally or push to GitHub and let GitHub Pages build.

## Repository

- **Remote**: `https://github.com/qianwang-lab/qianwang-lab.github.io.git`
- **Default branch**: `main`
- The repo follows the `<org>.github.io` pattern; GitHub Pages serves from `main`