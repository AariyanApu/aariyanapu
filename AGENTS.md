# Repository Guidelines

## Project Structure & Module Organization
- `README.md` drives the profile-style landing page; edit sections in place rather than splitting into partial files.
- Media assets live alongside the Markdown: hero artwork in `banner.webp` and `github-header-image.png`, with supplementary visuals inside `charts/` (e.g., `charts/bar_graph.png`).
- Keep new graphics in existing folders and reference them via relative Markdown paths so they render on GitHub without extra configuration.

## Build, Test, and Development Commands
- `npx markdownlint README.md AGENTS.md` — run before each push to catch heading, list, and spacing issues.
- `python -m http.server` — optional quick preview of image loading by serving the repository locally and opening `README.md` in a browser.

## Coding Style & Naming Conventions
- Author content in Markdown with ATX-style headings (`#`, `##`) and blank lines around block elements to preserve readability.
- Favor concise paragraphs and tables; keep lines under ~100 characters to avoid horizontal scroll in diffs.
- Name image files descriptively in lowercase with hyphens (`charts/contribution-trend.png`) and export to `.webp` when possible to minimize size.

## Testing Guidelines
- After updates, confirm all external badge and stats URLs still resolve; broken widgets degrade the profile page.
- Verify new images display as expected in GitHub’s Markdown preview and meet a ≤1 MB guideline for fast loading.
- Record manual checks in the pull request description when automated linting is the only scripted gate.

## Commit & Pull Request Guidelines
- Follow the existing concise style, but supply meaningful verbs: `docs: refresh github stats` or `assets: replace banner.webp` are preferred over generic "update".
- Scope each commit to a single concern (copy tweak, image swap, metrics refresh) to simplify review and rollback.
- For pull requests, include a short summary of visual changes, list affected sections, and attach before/after screenshots when altering media or layout.

## Asset Management Tips
- Compress large images with `npx imagemin-cli *.png --out-dir=charts` or an equivalent tool before committing.
- Store source design files outside the repo; only optimized exports belong here to keep the repository lightweight.
