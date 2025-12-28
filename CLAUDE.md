# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**The Kick Enterprise Club** — A political membership website for Harris County business leaders aligned with Democratic outcomes. The site targets a professional, politically-engaged audience with a design aesthetic inspired by NYT, The Atlantic, and CNN.

**Deadline:** January 5th

This is an Astro 5 project with Tailwind CSS v4.

## Commands

| Command | Action |
|--------|--------|
| `npm run dev` | Start local dev server at `localhost:4321` |
| `npm run build` | Build production site to `./dist/` |
| `npm run preview` | Preview build locally |
| `npm run astro ...` | Run Astro CLI commands |

## Stack

- **Astro 5** - Static site generator
- **Tailwind CSS v4** - Styling via Vite plugin (`@tailwindcss/vite`)
- **TypeScript** - Strict mode enabled

## Architecture

```
src/
├── assets/      # Static assets (images, fonts)
├── components/  # Astro components (`.astro` files)
├── layouts/     # Page layout templates
├── pages/       # File-based routing (`.astro` files become routes)
└── styles/      # Global styles, imports Tailwind via `@import "tailwindcss"`
```

### Key Files

- `astro.config.mjs` - Astro configuration, includes Tailwind Vite plugin
- `tsconfig.json` - Extends `astro/tsconfigs/strict`
- `src/styles/global.css` - Entry point for Tailwind CSS v4

### Tailwind CSS v4 Notes

Tailwind v4 uses Vite plugin integration instead of PostCSS. The setup is in `astro.config.mjs` and global styles import via `@import "tailwindcss"`.

### Component Pattern

Astro components use `.astro` extension with a frontmatter fence (`---`) for server-side JavaScript/TypeScript, followed by HTML template. Components can import and use other components and layouts.

## Future Site Structure (Post-MVP)

Full multi-page architecture planned for future development:

| Page | Route | Description |
|------|-------|-------------|
| About | `/about` | Why we exist, what we believe, our origin |
| Engagement | `/engagement` | Monthly leadership lunches, networking, landing for disaffected conservatives |
| Policy | `/policy` | BSB, Healthcare, Education, Energy, Tech & Innovation |
| Endorsements | `/endorsements` | Endorsed candidates (first cohort before 2026) |
| Events | `/events` | Upcoming events with RSVP & payment links |
| Blog | `/blog` | Articles, videos, content (excluded from MVP) |
| Membership | `/membership` | Benefits, tiers, payment links, member directory (coming Q1 2026) |

## Membership Tiers

- **Member** — $75/year
- **Kicker** — $125/year
- **Advisor** — $500/year (most common)
- **Senior Advisor** — $1,000/year (most common)
- **Partner** — $2,500/year
- **Executive Partner** — $5,000/year

## Content Reference

Detailed page content, copy, and wireframe notes are in `instruction.md`. Key sections include:

- **Homepage**: Hero with "The Kick Enterprise Club" branding, "What We're Building", "Who It's For", membership levels, bottom CTA with QR code
- **About**: Mission statement, beliefs, origin story
- **Engagement**: Monthly Leadership Lunches as signature series, emphasis on principled alignment and "politically homeless" conservatives
- **Events**: RSVP functionality, payment integration ($XX per guest)
- **Member Directory** & **Dealroom RFP Platform**: Coming Q1 2026

## MVP Scope: Single-Page Landing

The MVP is a **single-page landing page** at `/` that incorporates all major sections as scrollable sections. This reduces complexity while delivering complete information.

### Landing Page Sections (in order)

1. **Hero** — "The Kick Enterprise Club" headline, tagline, "Support The Kick" CTA button
2. **What We're Building** — Mission statement, bullet points on electing candidates, shaping policy, building infrastructure, creating space for disaffected conservatives
3. **Who It's For** — Target audience (founders, executives, investors, business leaders)
4. **About/Why We Exist** — Political outcomes shaped by strategy, not theater; capital with alignment
5. **What We Believe** — Bullet points on civic investment, infrastructure, showing up, moving in same direction, influence used to build
6. **Our Origin** — How The Kick was created by civic/business leaders seeing a gap
7. **Engagement** — Monthly Leadership Lunches signature series, principled alignment message
8. **Policy Areas** — BSB, Healthcare, Education, Energy, Tech & Innovation (brief overview)
9. **Endorsements** — Announcement that first cohort will be before 2026, "Join the List" CTA
10. **Upcoming Events** — Monthly Leadership Luncheon with RSVP & payment CTAs
11. **Membership** — All 6 tiers with pricing, "Join Now" CTA
12. **Bottom CTA** — "Let's Build Something That Lasts" with QR code placeholder

### Navigation

Fixed or sticky header with anchor links to each section. Smooth scroll behavior recommended.

## Design Guidance

- **Typography**: Clean serif or modern grotesque for clarity and professional tone
- **Backgrounds**: Muted architectural texture, abstract civic motifs, or Harris County visuals
- **Spacing**: Generous spacing, calm layout
- **CTAs**: Primary buttons should be clear and actionable ("Support The Kick", "Join Now", "Reserve Your Spot")
- **Visual hierarchy**: Use contrast and weight to emphasize key messages without being overly promotional
