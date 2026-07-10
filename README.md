# IPS Website

Marketing website for **Innovative People Solutions (IPS)** — an [Astro](https://astro.build)
static site with four routes: Home, Services, About, Contact.

Rebuilt from the design handoff in [`design_handoff_ips_website/`](./design_handoff_ips_website)
(see its `README.md` for the original design spec/tokens).

## Develop

```bash
npm install
npm run dev       # http://localhost:4321
```

## Build

```bash
npm run build     # outputs static site to dist/
npm run preview   # serve the built dist/ locally
```

## Project structure

```
src/
  components/   Header, Footer, and reusable UI (ServiceCard, TeamMember, ...)
  data/         content.ts — services/clients/values/team copy, shared across pages
  layouts/      Layout.astro — shared <head>, Header, Footer
  pages/        index.astro, services.astro, about.astro, contact.astro (real routes)
  styles/       global.css — design tokens (colors, type) and shared utility classes
public/
  assets/       logo + client logos served as static files
```

## Notes

- Contact form submits via a `mailto:` link to `sheerly@theips.us` (built client-side
  from the form fields) and then shows a success panel. No backend/email service is
  wired up — swap in a real form handler (e.g. Formspree) if you want submissions
  without relying on the visitor's email client.
- The About page's team section (names/roles/bios/avatars) is placeholder content —
  swap in real team info when available.
- Deployment: this outputs a fully static `dist/` folder, so it works with GitHub
  Pages, Netlify, Vercel, Cloudflare Pages, or any static host — confirm which one is
  actually wired up for theips.us and configure its build command as `npm run build`
  with publish directory `dist`.
