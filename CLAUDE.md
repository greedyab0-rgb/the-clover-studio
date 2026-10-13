# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working in this repository.

## Project

The Clover Studio is a single-page static marketing site for a handmade "forever flower" studio based in Dhaka, Bangladesh. It is one self-contained `index.html` (inline CSS + JS, no build step, no framework). Images live in the repo root and are referenced by relative path.

## Commands

- **Preview**: open `index.html` directly in a browser. No dev server, no install.
- **Deploy**: GitHub Pages via the workflow in `.github/workflows/pages.yml`. It runs on every push to `main` (plus manual `workflow_dispatch`). No command to run locally — CI handles it.
- **No tests, no linter.** The only "build" is committing changes.

## Architecture

- `index.html` — everything: semantic structure, inline `<style>` (with CSS custom properties for fluid type/spacing tokens, container queries, mobile-first media queries), and a small vanilla-JS menu toggle at the bottom.
- `.github/workflows/pages.yml` — deploys the repo root to GitHub Pages.
- `README.md` — setup/publish instructions.
- `CHANGES.md` — change log for the index page (encoding fixes, social link updates).
- `.claude/skills/` — installed skills (currently `responsive-design`).

## Conventions

- Relative image paths only; product photos must stay in the repo root alongside the page.
- Design tokens live in `:root` (`--text-*`, `--space-*` using `clamp()`). Use those rather than hardcoded sizes.
- Responsive behavior uses container queries (`container-type: inline-size`) and `@media (max-width)` breakpoints at 860px and 480px — mobile-first, so add overrides above the breakpoint, not below.
- The hero uses `min-height: 70svh` guarded by `@supports (height: 100dvh)` for mobile browser UI.

## Notes

- The site is pre-orders via DM (Instagram/Facebook); there is no e-commerce flow, cart, or backend.
- The `.claude/skills/responsive-design` skill is available — invoke it when making layout/ responsiveness changes.