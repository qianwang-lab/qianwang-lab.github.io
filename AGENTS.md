# Repository Guidelines

## Project Structure

```
_config.yml              — Site-wide config (theme, plugins, collections, defaults)
_data/navigation.yml     — Top-level nav menu items
_pages/                  — Static pages with explicit permalink in front matter
_posts/                  — Research highlights (YYYY-MM-DD-kebab-case-title.md)
assets/images/uploads/   — Media files (WordPress migration paths: YYYY/MM/filename)
index.html               — Homepage with hero + recent post loop
```

Pages route via `permalink:` front matter, not file path. Navigation is driven solely by `_data/navigation.yml`.

## Local Preview

Prerequisites: Ruby 3.2+ with Bundler on PATH. Add to `~/.bashrc` if not already present:

```bash
export PATH="$HOME/.local/share/gem/ruby/3.2.0/bin:$PATH"
```

Gems are installed to `vendor/bundle/` using the Ruby China mirror. If `bundle install` hangs:

```bash
bundle config set --local mirror.https://rubygems.org https://gems.ruby-china.com
```

Start the server:

```bash
cd ~/qianwang-lab-github/qianwang-lab.github.io
bundle exec jekyll serve          # Serves at http://127.0.0.1:4000
```

**Remote access (SSH from Mac):** Jekyll binds to loopback only. Add to your **Mac's** `~/.ssh/config`:

```
LocalForward 4000 127.0.0.1:4000
```

Then open **http://localhost:4000** in the Mac browser. Alternatively, forward manually: `ssh -L 4000:127.0.0.1:4000 <host>`.

## Coding Style & Naming Conventions

- Content files use Markdown (`.md`) with Jekyll front matter between `---` delimiters.
- Post filenames: `YYYY-MM-DD-kebab-case-title.md`.
- Publications: numbered lists with `**[Title](URL)**` and `*Journal*` in italics; author initials (`F. Li, Z. Shen, …, and Q. Wang`).
- Image paths: `/assets/images/uploads/YYYY/MM/filename`.
- Use HTML only when Markdown cannot achieve the layout (e.g., flex containers on biography).

## Adding Content

- **New page**: Create `.md` in `_pages/` with front matter (`title`, `permalink`, `layout: single`), then add to `_data/navigation.yml` if it needs a nav entry.
- **New post**: Add `.md` to `_posts/` — it appears automatically in the homepage loop.
- **New publication**: Append numbered entries to `_pages/journal-paper.md` or `_pages/conference-paper.md`.

## Commit & Pull Request Guidelines

- Commit messages: imperative mood with type prefix (`feat:`, `chore:`, `fix:`).
- Push directly to `main` for minor content updates; use PRs for structural changes.
- Deployment is automatic via GitHub Pages on push to `main`.
