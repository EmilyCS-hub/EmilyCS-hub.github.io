# AGENTS.md

Static GitHub Pages site — no build, no package manager, no tests, no lint, no CI.

## What this is
A single-page marketing/research site for "Not One Less" (NOLA), a BASEF 2026
science-fair project by Emily Sun. All content lives in `index.html` (inline
`<style>` + a small inline `<script>` at the bottom). There is no framework and
no external JS/CSS beyond Google Fonts.

## Editing
- Edit `index.html` directly; there is nothing to compile or run.
- Verify by opening `index.html` in a browser, or `python3 -m http.server` and
  open the printed URL.
- CSS custom properties (colors) are defined in `:root` at the top of the inline
  `<style>` block — reuse them rather than hardcoding hex values.

## Assets
- All images/PDFs live in `materials/` and are referenced from `index.html` by
  exact relative path (`materials/...`). Renaming a file breaks the page unless
  you also update every reference.

## Deployment & domain
- GitHub Pages serves the repo root on the default branch (`main`). Pushing to
  `main` deploys.
- `CNAME` contains `www.notonelesscare.com` — do not delete or alter it, or the
  custom domain breaks.

## Git
- Branches are named `main`, `feature/*`, and `stages/*`.
- `galaxy.html` (a separate legacy "Emily's Galaxy" page) exists on `main` and
  references remote images (`stars.png`, etc.) that are NOT in this repo. The
  `feature/nola-v1` branch stages its deletion. It is unrelated to the NOLA
  index page.
