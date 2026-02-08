# Plan: Personal Linktree Clone with AstroJS

**TL;DR**: Build a standalone, single-page Linktree-style site using AstroJS and your existing ShadCN-inspired design system. Profile + links stored in JSON, fully static, ready for deployment. Reuses colorscheme, typography, and component patterns from your portfolio.

## Steps

1. **Project scaffold** — Create a new Astro project with Tailwind CSS 4 using your existing config pattern from astro.config.mjs

2. **Copy design tokens** — Port over global.css with the ShadCN-inspired `@theme` block (background, foreground, muted, accent, border colors) and Inter font

3. **Create JSON data file** — `src/data/profile.json` with:
   - name, bio, avatar URL
   - links array: { title, url, icon?, description? }

4. **Build single-page layout** — `src/pages/index.astro` with:
   - Centered card container (mobile-first, max-width constrainted)
   - Avatar (circular, using your `rounded-full bg-muted overflow-hidden` pattern)
   - Name + short bio
   - Vertical list of link buttons (styled like your Button.astro component with `variant: outline`)

5. **Link component** — Create a `LinkButton.astro` component with hover effects matching your existing `transition-colors hover:bg-muted` pattern; optional icon support

6. **Optional enhancements**:
   - Favicon
   - Open Graph / meta tags for social sharing
   - Simple entrance animations (CSS only)

## Verification

- `npm run dev` — Preview locally at localhost:4321
- `npm run build` — Generates static files in `./dist/`
- Deploy to Vercel/Netlify/GitHub Pages

## Decisions

- Single page vs multi-page: **Single page** (Linktree is just one page)
- Standalone project vs integrated: **Standalone new project** (cleaner than adding to portfolio)
- JSON vs Markdown for data: **JSON** (simpler for structured link data)
