# Repository Guidelines

## Project Structure & Module Organization
This repo is a Quarto website for French-learning content. Root-level `.qmd` files such as `index.qmd`, `defi3.qmd`, `defi4.qmd`, and `af-nice-b1.qmd` define site pages. Section folders like `defi3/`, `defi4/`, `af-nice-b1/`, and `lenouveautaxi3/` hold local `_metadata.yml` files and image assets. Shared styling lives in `styles.css` and `custom.scss`. Generated site output is written to `docs/`; treat it as build output and regenerate it instead of editing HTML directly.

## Build, Test, and Development Commands
- `quarto preview` — starts the local site preview on the port set in `_quarto.yml` (9595).
- `quarto render` — rebuilds the full site into `docs/`.
- `quarto render defi4.qmd` — rebuilds a single page while editing.
- `open docs/index.html` — quick local check of rendered output after a build.

Run commands from the repository root.

## Coding Style & Naming Conventions
Use Quarto Markdown with clear section headings and short content blocks. Keep filenames lowercase with hyphens where needed; existing section names such as `af-nice-b1` and `le-nouveau-taxi-3` are the pattern to follow. Store page-specific assets beside the related content folder. Put shared visual changes in `styles.css` or `custom.scss`; keep page-only overrides close to the page, as in `defi4/styles.css`.

## Testing Guidelines
There is no automated test suite in this repo. Validate changes by running `quarto render` and checking for build errors. Then review the affected pages in `quarto preview` or the generated files under `docs/` to confirm navigation, images, and styling render correctly.

## Commit & Pull Request Guidelines
Recent history uses short, lowercase commit subjects such as `update` and `increase nav bar icon and font size`. Keep commits small and focused, but use more specific imperative messages when possible, for example `update defi4 cover image` or `adjust navbar spacing`. PRs should include: a short summary, affected pages or folders, screenshots for visual changes, and any notes about regenerated `docs/` output.

## Metadata Scope
Use `_quarto.yml` for site-wide defaults such as navigation, theme, render targets, and shared HTML options. Use folder-level `_metadata.yml` files for defaults that apply only within that section, such as `defi3/` or `af-nice-b1/`. Page front matter in an individual `.qmd` is the most specific override. Note that root pages like `defi3.qmd` are governed by `_quarto.yml` unless they define their own front matter; `defi3/_metadata.yml` applies only to files inside `defi3/`.

## Content & Publishing Notes
This site is deployed as a static site on GitHub Pages, with rendered output committed under `docs/`. `_quarto.yml` controls navigation, theme, render targets, and the `docs/` output directory. When adding a new section, update `_quarto.yml` so it appears in the navbar and renders with the site build.
