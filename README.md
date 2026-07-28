# wesleyfinck.org

Personal site built with [Astro](https://astro.build). Static output, deployed to Cloudflare Pages.

## Develop

```bash
npm install
npm run dev        # http://localhost:4321
```

## Build

```bash
npm run build      # outputs static site to dist/
npm run preview    # preview the production build locally
```

## Structure

```
public/
  favicon.svg
src/
  layouts/Base.astro       ← shared HTML shell (head / OG / footer)
  components/Footer.astro
  pages/index.astro        ← the single landing page
  styles/global.css
```

Add pages by dropping `.astro` files in `src/pages/`. Drop standalone `.html`
prototypes in `public/` (e.g. `public/experiments/foo.html` → `/experiments/foo.html`,
served verbatim).

## Deploy — Cloudflare Pages

Connect this repo in the Cloudflare Pages dashboard and set:

- **Build command:** `npm run build`
- **Output directory:** `dist`

Set the production domain in `astro.config.mjs` (`site`) for correct canonical URLs.
