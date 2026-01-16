# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Brand Guidelines

- **THE KICK** — The brand name must ALWAYS be written in all caps. Never use "The Kick", "the kick", or any other variation. This is a hard rule that applies across all content, copy, and code comments.

## Project Overview

**THE KICK Enterprise Club** — A political membership website for Harris County business leaders aligned with Democratic outcomes. The site targets a professional, politically-engaged audience with a design aesthetic inspired by NYT, The Atlantic, and CNN.

This is an Astro 5 project with custom CSS (no Tailwind).

## Commands

| Command | Action |
|--------|--------|
| `npm run dev` | Start local dev server at `localhost:4321` |
| `npm run build` | Build production site to `./dist/` |
| `npm run preview` | Preview build locally |
| `npm run astro ...` | Run Astro CLI commands |

## Stack

- **Astro 5** - Static site generator
- **Tailwind CSS v4** - Installed via Vite plugin (`@tailwindcss/vite`)
- **TypeScript** - Strict mode enabled

**Note:** While Tailwind is available, this project uses scoped `<style>` blocks in `.astro` files with custom CSS rather than Tailwind utility classes. This provides more control over the editorial design aesthetic.

## Architecture

```
src/
├── assets/      # Static assets (images, PDFs, fonts)
├── components/  # Astro components (Header.astro, Footer.astro, etc.)
├── layouts/     # Page layout templates (Layout.astro)
├── pages/       # File-based routing (`.astro` files become routes)
└── styles/      # Global styles
```

### Key Files

- `astro.config.mjs` - Astro configuration
- `tsconfig.json` - Extends `astro/tsconfigs/strict`
- `src/styles/global.css` - Global styles and font imports

## Current Site Structure

The site is live with the following pages:

| Page | Route | Description |
|------|-------|-------------|
| Homepage | `/` | Single-page landing with all sections (hero, mission, events, membership, etc.) |
| Articles | `/articles` | White papers and policy analysis (e.g., Texas HUB Program) |
| Links | `/links` | External resources (e.g., Find Your Representatives) |

### Planned Pages (Future)

| Page | Route | Description |
|------|-------|-------------|
| Events | `/events` | Upcoming events with RSVP & payment links |
| Membership | `/membership` | Benefits, tiers, payment links, member directory |

## Membership Tiers

- **Member** — $75/year
- **Kicker** — $125/year
- **Advisor** — $500/year (most common)
- **Senior Advisor** — $1,000/year (most common)
- **Partner** — $2,500/year
- **Executive Partner** — $5,000/year

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

**Font Stack:**
```css
/* Serif — article body, long-form content */
font-family: 'Georgia', 'Times New Roman', Times, serif;

/* Sans-serif — navigation, buttons, UI elements, headings */
font-family: 'Montserrat', sans-serif;
```

**Hierarchy:**
| Element | Size | Weight | Style |
|---------|------|--------|-------|
| H1 (Page title) | 24-32px | 700 | Sans-serif |
| H2 (Section title) | 28-32px | 700 | Sans-serif |
| H3 (Article heading) | 20-22px | 600 | Sans-serif |
| Body (article) | 17px | Regular | Serif, line-height 1.8 |
| Body (general) | 15-17px | Regular | Sans-serif or Serif |
| Labels, Meta | 13px | 500-600 | Sans-serif, optional uppercase |

### Layout & Grid

- **Container:** Max 1200px for main content
- **Gutters:** Desktop 48-64px, Mobile 24px
- **Content Width:** Full width for most pages; ~650px for focused text sections
- **Margins:** Generous white space between sections (60-80px vertical padding)

### Navigation

- **Position:** Sticky header
- **Style:** Text-focused, minimal, sans-serif (Montserrat)
- **Links:** Anchor links to main sections with smooth scroll
- **Layout:** "THE KICK" wordmark left, section links right, "Join Now" button

### Buttons & CTAs

**Hollow/Outline Style (Primary):**
- Transparent background
- Purple border (`#3105e9`)
- Purple text
- On hover: Purple background with white text
- Border radius: 2px (no pills)
- Padding: 14px 28px

**Usage:** "Join Now", "Subscribe", "Download", "Visit Site"

### Component Patterns

**Articles page:**
- Two-column layout on desktop (sidebar nav + content)
- Sidebar: 280px width, sticky positioning
- Article list items with bottom border dividers
- Article content: Georgia serif, 17px, line-height 1.8

**Links page:**
- Single-column layout with sidebar-style header
- "Links" heading: Uppercase, small (14px), gray
- List items with title, meta info, description, and CTA button
- Bottom border dividers between items

**Event/promotion blocks:**
- Two-column layout: text left, image/graphic right (desktop)
- Stacked on mobile
- Clear CTA button

### Interaction & UX

**Allowed:**
- Link color change on hover
- Subtle padding shifts on list items (8px)
- Smooth scroll for anchor navigation
- Purposeful, restrained transitions (0.2s ease)

**Avoid:**
- Bounce or elastic effects
- Over-animated transitions
- Scroll-jacking
- Heavy shadows
- Playful or decorative fonts
- Gradient backgrounds

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
- **Scoped Styles:** Use `<style>` blocks in `.astro` files
- **Components:** Minimal, content-first
- **CSS Approach:** Write custom CSS in scoped styles; Tailwind utilities are available but not typically used

Always optimize for:
✔ Readability
✔ Credibility
✔ Calm visual rhythm
✔ Conversion clarity (this is a membership site)
