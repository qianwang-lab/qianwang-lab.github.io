# Repository Guidelines

## Project Structure

```
_config.yml                          — Site-wide config (theme, plugins, collections, defaults)
_data/navigation.yml                 — Top-level nav menu items
_data/publications_journal.yml       — Journal paper data (structured YAML)
_data/publications_conference.yml    — Conference paper data (structured YAML)
_data/publications_misc.yml          — Misc publications (preprints, book chapters)
_pages/                              — Static pages with explicit permalink in front matter
  team.md, research.md, publication.md, alumni.md    — Current pages
  *_old.md                                            — Retired pages (biography, recruitment, etc.)
_research/                           — Research topic sub-pages (Jekyll collection)
  medical-image-synthesis.md         — Example topic page
_posts/                              — Research highlights (YYYY-MM-DD-kebab-case-title.md)
assets/css/style.css                 — Custom gradient+vibrant styles
assets/images/uploads/               — Media files (WordPress migration paths: YYYY/MM/filename)
assets/images/team/                  — Team member headshot photos
index.html                           — Homepage with hero, PI intro, research cards, publications, CTA
```

Pages route via `permalink:` front matter, not file path. Navigation is driven solely by `_data/navigation.yml`.

## Tech Stack

- **Jekyll** with **Beautiful Jekyll** theme (`daattali/beautiful-jekyll` via `jekyll-remote-theme`)
- **GitHub Pages** native deployment (push to `main`, auto-build)
- Plugins: `jekyll-feed`, `jekyll-seo-tag`, `jekyll-sitemap`
- Custom CSS: gradient+vibrant style in `assets/css/style.css` (loaded via `site-css` in `_config.yml`)

## Local Preview

Prerequisites: Ruby 3.2+ with Bundler on PATH. Add to `~/.bashrc` if not already present:

```bash
export PATH="$HOME/.local/share/gem/ruby/3.2.0/bin:$PATH"
```

Install and start the server:

```bash
cd ~/qianwang-lab-github/qianwang-lab.github.io
bundle install
bundle exec jekyll serve --host 0.0.0.0 --port 4000    # Serves at http://0.0.0.0:4000
```

**Important:** After any change to `_config.yml` (theme, plugins, collections, etc.), you must restart `jekyll serve`. Auto-regeneration only watches content files — it does NOT hot-reload config changes.

**Remote access (SSH from Mac):** Add to your **Mac's** `~/.ssh/config`:

```
LocalForward 4000 127.0.0.1:4000
```

Then open **http://localhost:4000** in the Mac browser. Alternatively, forward manually: `ssh -L 4000:127.0.0.1:4000 <host>`.

## Coding Style & Naming Conventions

- Content files use Markdown (`.md`) with Jekyll front matter between `---` delimiters.
- Post filenames: `YYYY-MM-DD-kebab-case-title.md`.
- Publications: stored as structured YAML in `_data/publications_*.yml`; each entry has `title`, `url`, `authors`, `journal`/`venue`, `year`, and optional fields (`volume`, `number`, `pages`, `month`, `note`, `location`).
- Image paths: `/assets/images/uploads/YYYY/MM/filename`.
- Team member photos: `/assets/images/team/` (placeholder initials used when no photo is available).
- Use HTML only when Markdown cannot achieve the layout (e.g., card grids, flex containers).
- Layouts: use `page` for static pages, `post` for blog posts. Do NOT use `home` (it appends a blog loop).

## Adding Content

- **New page**: Create `.md` in `_pages/` with front matter (`title`, `permalink`, `layout: page`), then add to `_data/navigation.yml` if it needs a nav entry.
- **New research topic**: Create `.md` in `_research/` with front matter (`title`, `permalink`, `layout: page`), then add a card linking to it in `_pages/research.md`.
- **New team member**: Add a `miil-member-card` div to `_pages/team.md` under the appropriate role heading.
- **New publication**: Append a YAML entry to `_data/publications_journal.yml` or `_data/publications_conference.yml`.
- **New alumni entry**: Add to the appropriate group in `_pages/alumni.md`.

## Retired Pages

The following old pages are kept with `_old` suffix and changed permalinks (e.g., `/biography-old/`) for reference. They can be deleted when no longer needed:

- `biography_old.md`, `team_old.md`, `research_old.md`, `publication_old.md`
- `journal-paper_old.md`, `conference-paper_old.md`
- `alumni_old.md`, `recruitment_old.md`, `students-supervised_old.md`

## Navigation Structure

```
Home (/)
Team (/team/)
Research (/research/)
  └─ Medical Image Synthesis (/research/medical-image-synthesis/)
Publication (/publication/)
  ├─ Journal tab  (from _data/publications_journal.yml)
  ├─ Conference tab (from _data/publications_conference.yml)
  └─ Misc tab (from _data/publications_misc.yml)
Alumni (/alumni/)
```

## Commit & Pull Request Guidelines

- Commit messages: imperative mood with type prefix (`feat:`, `chore:`, `fix:`).
- Push directly to `main` for minor content updates; use PRs for structural changes.
- Deployment is automatic via GitHub Pages on push to `main`.
