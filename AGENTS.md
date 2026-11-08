# AGENTS.md

Static GitHub Pages site — no build, no package manager, no tests, no lint, no CI.

## What this is
A single-page marketing/research site for "Not One Less" (NOLA), a BASEF 2026
science-fair project by Emily Sun. All content lives in `index.html` (inline
`<style>` + an inline `<script>` at the bottom). There is no framework and no
external JS/CSS beyond Google Fonts (Fraunces + Inter).

## Editing
- Edit `index.html` directly; there is nothing to compile or run.
- Verify by opening `index.html` in a browser, or `python3 -m http.server` and
  open the printed URL.
- CSS custom properties (colors, radius, shadow) are defined in `:root` at the
  top of the inline `<style>` block — reuse them rather than hardcoding hex
  values.
- The inline script drives three things: the footer year, the "Larger text"
  toggle (toggles `text-large` on `<html>`), and the demo video player. The
  player's playlist is the `tracks` array — its `file` paths and the markup IDs
  it queries (`track-list`, `demo-video`, `now-playing`, `now-desc`, `play-btn`)
  must stay in sync.

## Assets
- Images/PDFs live in `materials/` and are referenced from `index.html` by exact
  relative path (`materials/...`). Renaming a file breaks the page unless you
  also update every reference.
- Screenshots are in `materials/assets/` and `materials/assets/images/`; demo
  videos are in `materials/assets/videos/` and are referenced only from the
  `tracks` array in the inline script.

## Deployment & domain
- GitHub Pages serves the repo root on the default branch (`main`). Pushing to
  `main` deploys; other branches do not.
- `CNAME` contains `www.notonelesscare.com` — do not delete or alter it, or the
  custom domain breaks.

## Git
- Branch prefixes in use: `main`, `feature/*`, `local/*`, `older/*`, and
  `stages/*`.
- The pre-NOLA site is archived on `older/galaxy-web` and `stages/v0-0-0`. Those
  branches contain `galaxy.html` (legacy "Emily's Galaxy" page) which references
  remote images (`stars.png`, etc.) that are NOT in this repo. `galaxy.html` is
  no longer on `main` and is unrelated to the NOLA index page.
