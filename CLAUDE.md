# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Personal site for ridingmyzephyr.com. It's plain static HTML and CSS: no build step, package manager, framework, linter, or tests. To preview it, open `index.html` in a browser or serve the folder with any static server (for example, `python -m http.server`).

## Structure

- Four pages: `index.html` (home), `professional.html`, `exploratory.html`, `play.html`. Each one is a complete, standalone document.
- `style.css` is the only shared stylesheet. It's written in a compact, minified style with one rule per line. Match that style.
- There are no includes or templates. The `<head>` (Google Fonts link, stylesheet link), header/nav, and footer are copied into every page. A change to any of them has to be made in all four files.

## Conventions

- **Per-page accent color.** Each page sets `--accent` in an inline `<style>` in its `<head>`: home and play use `#2F7F86` (sea), professional uses `#C99A1E`, exploratory uses `#8A82C4`. Borders, links, and nav underlines all use `var(--accent)`.
- **Theme tokens** are on `:root` in `style.css` (`--haze`, `--ink`, `--sea`, `--sail`, `--lilac`, `--muted`). Dark mode redefines them under `prefers-color-scheme: dark`. Use these tokens, not raw colors.
- **Active nav item:** the current page's link gets `aria-current="page"` (the home page has none).
- **Fonts:** Bricolage Grotesque for headings and UI, Newsreader for body text.
- **Content blocks:** `.entry` is a dated row with `<time>` and `<h3>`, used for work history. `.note` is a left-bordered callout.
- **The `.streaks` SVG** is the animated "wind" motif. Its draw speed comes from the `--speed` custom property, and `play.html` changes it with a range slider. Motion is disabled under `prefers-reduced-motion`.
- The footer year is filled in by a one-line inline script on every page.
- Some pages still have template placeholder copy (for example, "Your Name" in the `play.html` footer, the `you@ridingmyzephyr.com` email, and the "Topic or question" notes). Don't treat it as final content.
