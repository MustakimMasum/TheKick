# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Brand Guidelines

- **THE KICK** — The brand name must ALWAYS be written in all caps. Never use "The Kick", "the kick", or any other variation. This is a hard rule that applies across all content, copy, and code comments.

## Project Overview

**THE KICK Enterprise Club** — A political membership website for Harris County business leaders aligned with Democratic outcomes. The site targets a professional, politically-engaged audience with a design aesthetic inspired by NYT, The Atlantic, and CNN.

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

- **Homepage**: Hero with "THE KICK Enterprise Club" branding, "What We're Building", "Who It's For", membership levels, bottom CTA with QR code
- **About**: Mission statement, beliefs, origin story
- **Engagement**: Monthly Leadership Lunches as signature series, emphasis on principled alignment and "politically homeless" conservatives
- **Events**: RSVP functionality, payment integration ($XX per guest)
- **Member Directory** & **Dealroom RFP Platform**: Coming Q1 2026

## MVP Scope: Single-Page Landing

The MVP is a **single-page landing page** at `/` that incorporates all major sections as scrollable sections. This reduces complexity while delivering complete information.

### Landing Page Sections (in order)

1. **Hero** — "THE KICK Enterprise Club" headline, tagline, "Support THE KICK" CTA button
2. **What We're Building** — Mission statement, bullet points on electing candidates, shaping policy, building infrastructure, creating space for disaffected conservatives
3. **Who It's For** — Target audience (founders, executives, investors, business leaders)
4. **About/Why We Exist** — Political outcomes shaped by strategy, not theater; capital with alignment
5. **What We Believe** — Bullet points on civic investment, infrastructure, showing up, moving in same direction, influence used to build
6. **Our Origin** — How THE KICK was created by civic/business leaders seeing a gap
7. **Engagement** — Monthly Leadership Lunches signature series, principled alignment message
8. **Policy Areas** — BSB, Healthcare, Education, Energy, Tech & Innovation (brief overview)
9. **Endorsements** — Announcement that first cohort will be before 2026, "Join the List" CTA
10. **Upcoming Events** — Monthly Leadership Luncheon with RSVP & payment CTAs
11. **Membership** — All 6 tiers with pricing, "Join Now" CTA
12. **Bottom CTA** — "Let's Build Something That Lasts" with QR code placeholder

### Navigation

Fixed or sticky header with anchor links to each section. Smooth scroll behavior recommended.

## Design System & Style Guide

Inspired by **The Atlantic**'s editorial design aesthetic — "bold but classical, beautiful and urgent" — adapted for a political membership organization. Focus on sophistication, credibility, and readability.

**Important:** This is a **political membership site**, not a news publication. Use the editorial aesthetic for trust and authority, but adapt for conversion and membership communication.

### Design Philosophy

Prioritize clarity, hierarchy, and readability. Design must feel authoritative, calm, and intellectual. Avoid flashy UI, gradients, excessive animations, or startup-style visuals.

**Core adjectives to embody:**
- **Relevant** — Current, forward-thinking
- **Credible** — Serious, trustworthy, established
- **Elegant** — Refined, not garish or trendy

### Color Palette

| Role | Color | Usage |
|------|-------|-------|
| **Primary Accent** | Purple (`#3105e9`) | CTAs, links, logo/wordmark, key emphasis |
| **Base** | White (`#FFFFFF`) | Backgrounds, clean foundation |
| **Text Primary** | Near-black (`#1A1A1A`) | Headlines, body text |
| **Text Secondary** | Muted gray (`#666666`) | Supporting text, labels |
| **Section Dividers** | Light gray (`#E5E5E5`) | Horizontal rules, borders |

**Accent color usage:** Sparingly — CTAs, section headers, links, hover states. Never use gradients or neon colors.

**IMPORTANT:** Always use `#3105e9` for the primary accent color. Do NOT use `#6B1986` or any other purple shade.

### Typography

**Font Stack (one serif + one sans-serif):**
```css
/* Serif — headlines, body, mission content (mimics AGaramond Pro) */
font-family: 'Georgia', 'Times New Roman', Times, serif;

/* Sans-serif — navigation, buttons, tier labels, UI (mimics Graphik) */
font-family: 'Inter', system-ui, -apple-system, sans-serif;
```

**Hierarchy:**
| Element | Size | Weight | Style |
|---------|------|--------|-------|
| H1 (Hero title) | 40-52px | Bold | Serif |
| H2 (Section title) | 28-32px | Semibold | Serif, italic optional |
| H3 (Subsection/Tier) | 20-24px | Semibold | Serif or Sans |
| Body | 17-19px | Regular | Serif, line-height 1.6-1.8 |
| Labels, Meta | 13-14px | Medium | Sans-serif, uppercase |

**Key techniques:**
- Use *italics* and larger size for emphasis — avoid heavy bold
- Headlines dominate visually
- Typography over decoration

### Layout & Grid

- **Grid:** 12-column responsive
- **Gutters:** Desktop 48-64px, Mobile 24-32px
- **Content Width:** Max ~1200px for main container; ~650px for focused text sections
- **Responsive:** Desktop (3-4 col) → Tablet (2 col) → Mobile (1 col)
- **Margins:** Generous white space between sections

### Navigation

- **Position:** Sticky header
- **Style:** Text-focused, minimal, sans-serif
- **Links:** Anchor links to main sections with smooth scroll
- **Layout:** "THE KICK" wordmark left, section links right

### Buttons & CTAs

| Type | Style | Usage |
|------|-------|-------|
| **Primary** | Solid red bg, white text, rectangular | "Support THE KICK", "Join Now", "RSVP" |
| **Secondary** | White bg, red border, red text | "Learn More", "View Tiers" |
| **Tertiary** | Underlined text link | In-content navigation |

- Shape: Rectangular, max 2-4px border radius (no pills)
- Padding: 14-18px vertical, 28-36px horizontal
- Typography-forward, not heavily styled

### Component Patterns

**Section containers:**
- Generous vertical padding (80-120px between sections)
- Optional light divider line between sections
- No colored backgrounds — white space is the separator

**Membership tiers display:**
- List or card layout
- Price prominent (serif, larger)
- Tier name in sans-serif, uppercase, accent color
- "Most common" badge on Advisor/Senior Advisor

**Event/promotion blocks:**
- Two-column layout: text left, image/graphic right (desktop)
- Stacked on mobile
- Clear CTA button

### Interaction & UX

**Allowed:**
- Link underline or color change on hover
- Subtle elevation on hover
- Smooth scroll for anchor navigation
- Purposeful, restrained animations

**Avoid:**
- Bounce or elastic effects
- Over-animated transitions
- Scroll-jacking
- Heavy shadows
- Playful or decorative fonts

### Imagery

- Style: Professional, documentary, architectural, or civic
- No stock-photo smiles or generic business imagery
- Rectangular, clean aspect ratios
- Support text, not overpower it

### Hard Constraints (Do NOT)

| ❌ | Avoid |
|----|-------|
| | Playful/display fonts |
| | Gradient backgrounds |
| | Borders on everything |
| | Center-aligned body text (left-align only) |
| | Heavy shadows |
| | Non-accent bright colors |
| | Rounded pill buttons |
| | Excessive animations |

### Code Output Guidelines

- **HTML/CSS:** Semantic, clean
- **Tailwind:** Restrained utilities, prefer theme values over arbitrary
- **Components:** Minimal, content-first

Always optimize for:
✔ Readability
✔ Credibility
✔ Calm visual rhythm
✔ Conversion clarity (this is a membership site)
