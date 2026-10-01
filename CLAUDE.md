# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Single-page site for Mike Bauknecht's software consulting, served at bauknecht.ing (GitHub Pages, see `CNAME`). It's plain static HTML and CSS: no build step, package manager, framework, linter, or tests. To preview it, open `index.html` in a browser or serve the folder with any static server (for example, `python -m http.server`).

## Structure

- One page: `index.html`. It's hand-formatted with 4-space indentation and one block element per line, so the nesting is visible. Keep it that way (short inline elements like `<span>` stay on their parent's line). Sections (`#services`, `#experience`, `#contact`) are linked from the header nav as in-page anchors.
- `notes/` is git-ignored and holds working notes that stay local, such as `notes/experience-interview.md`, the open questions and verification checklist for the Experience section. Check it when resuming that work.
- `style.css` is the only stylesheet. It's written in a compact, minified style with one rule per line. Match that style.

## Conventions

- **Theme tokens** are on `:root` in `style.css`: `--bg`, `--surface`, `--ink`, `--muted`, `--line`, `--accent` (steel blue, used for links and buttons), `--accent-ink`, `--gold` (used sparingly for the featured card and price), and `--hero*` for the dark navy hero band. Dark mode redefines them under `prefers-color-scheme: dark`. Use these tokens, not raw colors.
- **Fonts:** Inter Tight for headings, Inter for body and UI.
- **Layout:** each page section is a full-width `<section>` with a `.wrap` inside. `.hero` is the dark intro band. `.contact` sits on the surface color.
- **Components:** `.btn` (with `.btn-ghost` and `.btn-sm` variants), `.card` in a `.grid` for services (`.featured` adds the gold top border), `.skills` for the bulleted skill list, and `.timeline` (an `<ol>` of `<time>` plus `<h3>` rows, with the employer in an `<h3> span`) for work history.
- On narrow screens (40rem and below), the header nav shows only the "Get in touch" button.
- The footer year is filled in by a one-line inline script.
