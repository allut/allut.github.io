# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Static personal website hosted on GitHub Pages (`allut.github.io`). No build step, bundler, or framework — files are served directly.

## Structure

- `index.html` — landing / home page
- `cv.html` — CV / profile page
- `services.html` — freelance services offering page
- `claude-anvil.html` — product page for the claude-anvil plugin
- `styles.css` — shared stylesheet for all pages
- `theme.js` — inline script (loaded before `<body>`) that reads/writes `localStorage` and sets `data-theme` on `<html>` to avoid flash of wrong theme
- `favicon.svg` — SVG favicon (dark rounded square with amber italic "AL")
- `portrait.jpg` — profile photo used in the hero

## Development

Open any `.html` file directly in a browser. No server or build process required.

To preview with live reload, a simple option is:
```
npx serve .
```

## Architecture

All pages share `styles.css` and a shared navigation bar (`site-nav`). The CSS uses CSS custom properties (`--bg`, `--accent`, etc.) defined in `:root` for theming — a "Northern Precision" design system with dark and light modes (deep navy/charcoal backgrounds or warm off-white, amber accent `#c07a40`, three typefaces: Instrument Serif, JetBrains Mono, DM Sans). Light mode tokens are in the `[data-theme="light"]` block; `theme.js` switches the attribute and persists the preference to `localStorage`.

Responsive breakpoints: 900px (tablet) and 720px (mobile). Grid layouts (`skills-grid`, `impact-grid`, `offers-grid`, `problem-grid`, `compact-steps`) collapse to single-column on mobile via media queries.
