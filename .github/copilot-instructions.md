## Purpose
Provide concise, actionable guidance for AI coding agents working on this repository: a small static HTML/CSS project deployed via GitHub Pages.

## Big picture
- This is a static markup site: the core assets are `index.html`, `About.md`, `css/styles.css`, and `images/`.
- No build step or server-side code. Changes are plain file edits and are served as static files (GitHub Pages).

## Key files / directories
- `index.html` — main entry page and primary layout to update when changing navigation or structure.
- `About.md` — content page (Markdown) mirrored in the site; update concurrently with HTML if you change nav links.
- `css/styles.css` — all styling lives here; prefer adding component-scoped classes rather than global selectors when possible.
- `images/` — static images; reference using relative paths (e.g., `images/logo.png`).
- `.prettierrc.json` — formatting rules; run Prettier if available in the environment before committing HTML/CSS changes.
- `README.md` — contains the published GitHub Pages URL; keep it updated if deployment changes.

## Developer workflows (practical commands)
- Preview locally (from repository root):
  - Python 3: `python -m http.server 8000` then open `http://localhost:8000`.
  - Or use VS Code Live Server extension to preview `index.html`.
- Format files: run Prettier (if installed in your environment) or rely on the editor formatting rules defined by `.prettierrc.json`.

## Project-specific conventions
- Paths are relative: update references in `index.html` and other HTML files to use `css/` and `images/` relative paths.
- Keep CSS in `css/styles.css` rather than adding inline styles in HTML files.
- When changing the site structure (e.g., adding pages), mirror navigation updates in both `index.html` and `About.md`.

## Integration points
- GitHub Pages: this repository is published as a static site — push to the default branch (or the branch configured for Pages) to publish changes.
- No external build or CI is present in the repo; assume manual preview and push workflow.

## Agent guidance (how to make safe, helpful edits)
- Make minimal, targeted edits: update the exact file(s) that require change (e.g., adjust `css/styles.css` when fixing visual regressions).
- Preserve relative paths. Example: if adding an image referenced in `index.html`, add the file under `images/` and set the src to `images/your.png`.
- When modifying markup structure, ensure CSS selectors in `css/styles.css` still apply or are updated accordingly.
- Do not remove `About.md` or `README.md`; they contain content and the published URL.

## Examples
- To change the header color: edit `css/styles.css` (search for `.header` or similar selectors) and run a local preview.
- To add a new page `contact.html`: create the file at repo root, add navigation link in `index.html`, and place assets in `images/` and styles in `css/styles.css`.

## When you are uncertain
- If a requested change touches multiple files (HTML + CSS + images), propose the minimal patch and ask the maintainer before large restructures.

---
If any section is unclear or you want the agent to follow stricter commit/message rules, tell me where to refine this file.
