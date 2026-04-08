# Klarity International — Project Guide

## What This Is
Single-page marketing site for **Klarity International**, an executive communication coaching practice founded by **Klara Farkas**. Static site built with Astro, deployed to GitHub Pages.

## Tech Stack
- **Framework**: Astro (latest stable)
- **Styling**: Plain CSS with CSS custom properties (no Tailwind, no CSS frameworks)
- **JavaScript**: Vanilla JS only — no React, Vue, or other UI frameworks
- **Fonts**: Google Fonts — Cormorant Garamond (display) + Outfit (body)
- **Deployment**: GitHub Pages via `astro build` → static output
- **Images**: Optimized via Astro's built-in `<Image />` component where possible

## Project Structure
```
src/
  layouts/
    Layout.astro          # Base HTML shell (head, fonts, global styles)
  components/
    Nav.astro             # Fixed nav with mobile hamburger
    Hero.astro            # Hero section (split: copy left, photo right)
    Credibility.astro     # Dark strip with 3 stats
    WhatIDo.astro         # 4-card grid — what Klara helps with
    WhoIWorkWith.astro    # 4-item checklist grid
    Process.astro         # Dark section, 3-step Clarify/Communicate/Align
    Services.astro        # 3 service cards
    Testimonials.astro    # 2x2 quote cards (placeholders for now)
    About.astro           # Photo + bio side-by-side
    Clients.astro         # "Trusted by" logo strip (text-based)
    FinalCTA.astro        # Dark CTA section
    Footer.astro          # Simple footer
  pages/
    index.astro           # Assembles all components in order
  styles/
    global.css            # All CSS custom properties + global resets + all section styles
public/
  images/
    klara-hero.jpg        # Color headshot (hero section)
    klara-about.jpg       # B&W side profile (about section)
    klarity-logo.jpg      # Klarity International logo
```

## Design System

### Colors (from logo)
```css
--blue: #3BA4C4;
--blue-deep: #2A8BA8;
--blue-light: #E8F4F8;
--blue-mist: #F3F9FB;
--gold: #B8A45C;
--gold-light: #D4C97A;
--charcoal: #2C3E44;
--charcoal-light: #3D5159;
--grey-warm: #6B7D85;
--grey-mid: #94A3A9;
--grey-light: #C8D1D4;
--grey-pale: #E9EDEF;
--cream: #FAFBFB;
--white: #FFFFFF;
```

### Typography
- **Display/headings**: `'Cormorant Garamond', Georgia, serif` — weights 300, 400, 500
- **Body/UI**: `'Outfit', 'Helvetica Neue', sans-serif` — weights 300, 400, 500, 600
- Section headings use `<em>` for italic accent words colored `--blue-deep`

### Design Principles
- Executive and warm — NOT life-coach-y or woo-woo
- Generous whitespace, clean hierarchy
- Turquoise/blue primary with charcoal anchoring dark sections
- Gold accents used sparingly (process section tags, CTA section tags)
- Subtle scroll-reveal animations via IntersectionObserver
- Mobile-first responsive: hamburger nav, single-column stacking

### Contact
All CTAs link to: `mailto:klara@klarityinternational.com` with appropriate subject lines.
LinkedIn: https://www.linkedin.com/in/klarafarkas

## Commands
- `npm run dev` — local dev server
- `npm run build` — production build
- `npm run preview` — preview production build locally

## Deployment
GitHub Pages. The `astro.config.mjs` should set:
```js
export default defineConfig({
  site: 'https://klarityinternational.com',
  output: 'static',
});
```

## Content Notes
- Testimonials are **placeholders** — marked with italic note. Will be replaced with real quotes later.
- Copy is finalized and approved by client. Do not rewrite.
- Images are provided as JPGs in `public/images/`.
