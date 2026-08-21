# ShinyVale Wiki — maintenance guide

The player wiki for ShinyVale SMP, built with [MkDocs](https://www.mkdocs.org/) + [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/). Every page is a plain Markdown file — no database, no build step required to edit content.

## Requirements

Python 3.12 with MkDocs Material installed:

```powershell
python -m pip install mkdocs-material
```

(Already installed on this machine at `C:\Users\Administrator\AppData\Local\Programs\Python\Python312`. If `python`/`mkdocs` aren't found in a given terminal, use the full path: `C:\Users\Administrator\AppData\Local\Programs\Python\Python312\python.exe -m mkdocs ...`)

## Preview locally

From this folder (`shinyvale-wiki/`):

```powershell
python -m mkdocs serve
```

Opens a live-reloading preview at **http://127.0.0.1:8000** — edit any `.md` file and the browser updates automatically.

## Build for production

```powershell
python -m mkdocs build
```

Outputs a fully static site to `site/` — every file in there is what you upload to a host. Add `--strict` to fail the build if any internal link is broken (recommended before publishing an update):

```powershell
python -m mkdocs build --strict
```

## How to add a new page

1. Create a new `.md` file under `docs/` (pick whichever subfolder fits — `gameplay/`, `commands/`, `features/`, `help/`, etc.).
2. Start it with a frontmatter block:
   ```markdown
   ---
   title: Page Title
   description: One sentence for search engines and link previews.
   ---

   # Page Title

   Your content here.
   ```
3. Add it to the `nav:` section of `mkdocs.yml`, in the sidebar location you want it to appear.

## How to add a sidebar section

Edit the `nav:` block in `mkdocs.yml` — it's a plain nested list. Each top-level entry becomes a tab; sub-entries become the sidebar under that tab.

## How to update a command

Commands live as plain Markdown tables inside the relevant page under `docs/commands/`. Find the table, edit the row. No other file needs to change.

**Before publishing a command change:** verify it against the live server config — see the "Accuracy" notes in the project handoff for what's already confirmed vs. what to double-check first.

## How to update a rule

Edit `docs/rules/index.md`. This page is meant to mirror the live in-game `/rules` GUI (`plugins\DeluxeMenus\gui_menus\rules.yml`) — if that changes, update this page to match, and vice versa; don't let them drift apart.

## Design system

All custom styling lives in one file: `docs/stylesheets/shinyvale.css`. Color tokens are defined once per theme (`[data-md-color-scheme="shinyvale-light"]` / `[data-md-color-dark"]`) — change a value there and it updates everywhere. Reusable page components (`.sv-hero`, `.sv-grid` / `.sv-card`, `.sv-cmd-strip`) are documented inline in that file and can be reused in any page's Markdown via raw HTML blocks — see any existing page for the pattern.

## Logo / branding

`docs/assets/images/logo.png` and `favicon.png` are ShinyVale's actual in-game server-logo texture (pulled from the resource pack). Replace those files (same filenames) to update branding site-wide.
