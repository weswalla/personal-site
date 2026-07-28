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
  experiments/     ← standalone HTML prototypes, served verbatim
    hello.html     →  /experiments/hello.html
  favicon.svg
src/
  layouts/Base.astro
  components/Header.astro, Footer.astro
  pages/
    index.astro        ← bio / landing
    portfolio.astro
    experiments.astro  ← auto-lists every *.html in public/experiments/
    contact.astro
  styles/global.css
```

## Adding an experiment

Drop any self-contained `.html` file into `public/experiments/`. It is:

- served as-is at `/experiments/<filename>.html`
- listed automatically on the `/experiments` page (filename is titleized)

No build config or route changes needed.

## Deploy — Cloudflare Pages

Connect this repo in the Cloudflare Pages dashboard and set:

- **Build command:** `npm run build`
- **Output directory:** `dist`

Custom domain + SSL are configured in the Pages dashboard. Remember to set the
production domain in `astro.config.mjs` (`site`) so canonical URLs are correct.
