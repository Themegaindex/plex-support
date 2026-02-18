# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # Start dev server at localhost:4321
npm run build     # Build production site to ./dist/
npm run preview   # Preview production build locally
npm run astro     # Run Astro CLI (e.g., astro add, astro check)
```

No test or lint scripts are configured.

## Project Overview

**PrimeTime** is a German-language support/documentation website for a Plex-based streaming service. Built with **Astro 5** as a static site with no framework integrations (pure Astro components).

## Architecture

### Layout System

- `src/layouts/Layout.astro` — Base template wrapping every page. Accepts `title` and `description` props, imports Navigation and Footer, loads global CSS and the Inter font.

### Pages (`src/pages/`)

- `index.astro` — Landing page with quick-access cards
- `dienste.astro` — Service offerings (film/series libraries, payment methods, support scope)
- `faq.astro` — FAQ with client-side search and category filtering (accordion UI)
- `hilfe.astro` — Detailed help guide (7 major sections: streaming issues, 4K, settings, account setup, etc.)
- `kontakt.astro` — Contact page with a form that triggers `mailto:` on submission

### Components (`src/components/`)

- `Navigation.astro` — Sticky header with mobile hamburger menu and active-page highlighting (uses inline `<script>`)
- `Footer.astro` — Multi-column footer with dynamic copyright year

### Styling

- `src/styles/global.css` — Single CSS file defining all custom properties (dark theme, color system, spacing scale, typography, shadows, transitions). All components use these CSS variables — no utility framework.

## Key Technical Details

- **Language**: All content is in German.
- **Supabase**: Credentials are in `.env` (`VITE_SUPABASE_URL`, `VITE_SUPABASE_ANON_KEY`). The integration is configured but not visibly used in current page code — any backend functionality would go through Supabase.
- **TypeScript**: Strict mode via `astro/tsconfigs/strict`.
- **Interactivity**: Implemented via inline `<script>` tags in `.astro` files (no JS framework). Examples: FAQ accordion/search filter, mobile nav toggle, contact form validation.
- **Container max-width**: 1200px, defined in `--container-max-width` CSS variable.

## language

- immer deutsch schreiben und antworten
