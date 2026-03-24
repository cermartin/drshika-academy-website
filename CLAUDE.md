# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

DrShika Academy is a static single-page marketing website for a London-based career coaching business. It was rebuilt from a Webflow draft (`drshika4.webflow.io`) and is intended to become the permanent business site.

**No build step required.** Open `index.html` directly in a browser or serve with any static file server:
```bash
npx serve .
# or
python -m http.server 8080
```

## Architecture

The entire site lives in a single file: [index.html](index.html)

- All CSS is embedded in a `<style>` block (lines ~15–229) — no external stylesheets
- No JavaScript frameworks; the only JS is `onsubmit="return false"` on forms (placeholder — forms are not yet functional)
- Fonts loaded from Google Fonts: `Inter` (body) and `Playfair Display` (headings)
- Images live in [assets/images/](assets/images/) — 65+ files including headshots, credential photos, and logo variants
- [CONTEXT.md](CONTEXT.md) is the single source of truth for all brand content: copy, testimonials, masterclass details, image file purposes, and design notes

## Design System

CSS custom properties defined at `:root`:
- `--gold: #c9a84c` / `--gold-light: #e8c96a` — primary accent
- `--dark: #0a0a0f` / `--dark-2: #12121a` / `--dark-3: #1a1a26` — background layers
- `--text: #f0ede8` / `--text-muted: #9e9a94` — typography

Layout uses CSS Grid and Flexbox with `clamp()` for fluid/responsive sizing. No breakpoint-heavy media queries.

## Site Sections (in order)

All sections use anchor IDs: `#hero`, `#pillars`, `#superpowers`, `#about`, `#testimonials`, `#resources`, `#cta-banner`, `#contact`

Masterclass cards: Networking (LIVE), Interview Pro, Personal Brand, LinkedIn Masterclass (last three are COMING SOON).

## Known Gaps / Planned Work

- Forms (contact + newsletter) need backend integration — currently disabled with `onsubmit="return false"`
- About section has placeholder content — full bio, credential photos, and expanded story should come from `CONTEXT.md` and the images listed there
- Resources section has static blog card UI but no actual blog functionality
- The full site will eventually expand to separate pages (Superpowers, About Us, Resources, Contact) — currently all in one `index.html`
- `assets/The H! Career Accelerator.pdf` and `assets/VID-20260323-WA0001.mp4` are available for use in the About/credentials section
