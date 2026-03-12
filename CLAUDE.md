# Project Guidelines

## Astro Best Practices

### Images
- Always use `import { Image } from 'astro:assets'` instead of raw `<img>` tags for automatic optimization (WebP, sizing).
- Place images in `src/assets/` (not `public/`) so Astro can process and optimize them.
- For above-the-fold images (hero, header), always set `loading="eager"` — Astro defaults to `loading="lazy"` which hurts LCP for visible content.
- Below-the-fold images should keep the default `loading="lazy"`.

### Links & Navigation
- Never use `href="#"` on anchor tags — use `href="/"` for home/logo links to pass HTML validation and Astro audits.
- Use `href="#section-id"` only for in-page anchor navigation to real section IDs.

## Deployment
- Hosting: Cloudflare Pages (project: `carloszambrana-dev`)
- Deploy command: `CLOUDFLARE_ACCOUNT_ID=6259d8ec59ab656d08235f0d61c3512e npx wrangler pages deploy dist --project-name=carloszambrana-dev`
- Always run `npm run build` before deploying.
- GitHub repo: https://github.com/carzam87/carloszambrana.dev
