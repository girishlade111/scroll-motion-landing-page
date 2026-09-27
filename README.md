# Scroll Motion Landing Page

A full-screen, scroll-driven landing page template built with Next.js — each viewport-height section reveals with buttery Framer Motion animations as you scroll. Includes a fixed dot navigation, a spring-animated scroll progress bar, and a decorative squares background component. A clean starting point for product launches, portfolios, and marketing one-pagers.

## What it does

- Renders a sequence of full-screen content sections defined in `app/components/constants/sections.tsx`.
- Tracks scroll position inside a scroll container and highlights the active section in a fixed dot-nav rail.
- Shows a spring-physics scroll progress bar pinned to the top of the viewport.
- Smooth-scrolls to any section when a nav dot is clicked.
- Ships with shadcn/ui primitives (`badge`, squares-background) and a shared `Layout`/`Section` composition.

## Features

- Scroll-linked section activation with per-section highlight state
- Framer Motion `useScroll` + `useSpring` progress bar
- Fixed dot navigation rail with smooth scroll-to-section
- Animated squares/canvas background component
- Dark, minimal marketing aesthetic (Tailwind CSS)
- Fully client-side — no backend, no API routes, static-export ready

## Tech stack

| Layer      | Technology                          |
|------------|-------------------------------------|
| Framework  | Next.js 15 (App Router)             |
| UI         | React 19, TypeScript                |
| Animation  | Framer Motion                       |
| Styling    | Tailwind CSS 3.4, tailwindcss-animate |
| Components | shadcn/ui (Radix UI primitives), Lucide icons |
| Theming    | next-themes                         |
| Analytics  | @vercel/analytics                   |

## Quick start

Requirements: Node.js 18+ and pnpm (or npm).

```bash
# install dependencies
pnpm install

# start the dev server
pnpm dev
# open http://localhost:3000

# production build (static export into ./out)
pnpm build
```

If peer-dependency conflicts block npm installs, use `npm install --legacy-peer-deps`.

## Project structure

```
app/
  page.tsx                  # entry: renders LandingPage
  layout.tsx                # root layout (fonts, metadata, theme)
  globals.css               # Tailwind + global styles
  components/
    LandingPage.tsx         # scroll container, progress bar, dot nav
    Layout.tsx              # shared page chrome
    Section.tsx             # single full-screen section
    constants/sections.tsx  # section content definitions
    ui/                     # shadcn/ui primitives
  lib/utils.ts              # cn() helper
  types/index.ts            # shared TypeScript types
public/                     # static assets
styles/                     # additional stylesheets
```

## Customizing the sections

Edit `app/components/constants/sections.tsx` — add, remove, or reorder section objects. The dot nav and scroll math adapt automatically since they are derived from the same array.

## Environment variables

None required. The app is fully client-side with no secrets.

## Deployment

The app has no server-side code (no `/api` routes, no server actions) and is exported as a static site (`output: 'export'` in `next.config.mjs`):

```bash
pnpm build   # emits a static site into ./out
```

Deploy the `out/` directory to any static host (GitHub Pages, Cloudflare Pages, Netlify).

> **Note on `basePath`:** `next.config.mjs` currently sets `basePath: '/scroll-motion-landing-page'` because this project is hosted under a GitHub Pages subpath (`https://girishlade111.github.io/scroll-motion-landing-page`). If you deploy to a domain root (Vercel, custom domain), remove the `basePath` line before building.

## License

Free to use and modify.

---

Built by Girish Lade · https://ladestack.in
