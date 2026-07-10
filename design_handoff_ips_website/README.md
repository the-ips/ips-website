# Handoff: IPS — Innovative People Solutions Website

## Overview
Marketing website for **Innovative People Solutions (IPS)**, a boutique HR & Talent consulting firm. The site presents IPS's services, approach, team, and clients, and drives visitors to book a consultation. It is a four-page single-site experience: **Home, Services, About, Contact.**

## About the Design Files
The file in this bundle (`IPS Website.dc.html`) is a **design reference created in HTML** — a prototype showing intended look and behavior, **not production code to copy directly.** It is authored as a "Design Component" (a streaming HTML format) and uses an internal state-driven router to switch between the four pages within one file.

Your task is to **recreate this design in the target codebase's existing environment** (React, Vue, Next.js, Astro, etc.) using its established patterns, routing, and component conventions. If no environment exists yet, choose the most appropriate framework for a marketing site (e.g. Next.js or Astro) and implement there. The four "pages" should become real routes (`/`, `/services`, `/about`, `/contact`), not client-side state swaps.

## Fidelity
**High-fidelity (hifi).** Final colors, typography, spacing, and copy are specified below and should be recreated faithfully. Rebuild the UI pixel-close using the codebase's own component/styling libraries.

---

## Design Tokens

### Colors
| Token | Hex | Usage |
|---|---|---|
| Green (primary) | `#3a4d3c` | Buttons, wordmark, links, headings accents |
| Green deep | `#2c3a2e` | Dark sections, footer, headline text, button hover |
| Sage (accent) | `#8fa389` | Eyebrow labels, numerals, rules, link hover |
| Greige | `#e0ddd0` | Logo backing tile |
| Greige panel | `#e6e3d7` / `#eceadf` | Striped image placeholders |
| Section tint | `#f2efe4` | Stat strip, CTA band, alt sections |
| Background (page) | `#f7f5ed` | Body / default background |
| Card | `#fdfcf6` | Cards on hover, contact form panel |
| Text body | `#5b6157` | Paragraph copy |
| Text ink | `#2b332b` | Default text color |
| Text muted | `#71766a` | Secondary labels |
| Footer text | `#c3cdba` / `#a7b8a0` | Footer body / muted |
| Hairline | `rgba(58,77,60,0.12)` | Borders, dividers, grid gaps |

### Typography
- **Display / headings:** `'Cormorant Garamond', serif` — weight 500 (occasionally 600 for the wordmark). High-contrast editorial serif.
- **Body / UI / labels:** `'Jost', sans-serif` — weights 300 (body), 400/500 (UI), 600.
- Load both from Google Fonts (`Cormorant+Garamond:ital,wght@0,400;0,500;0,600;1,400` and `Jost:wght@300;400;500;600`).

Type scale (approx):
- Hero H1: Cormorant 76px / line-height 1.02 / letter-spacing -1px / weight 500
- Page H1: Cormorant 60–66px
- Section H2: Cormorant 46–56px
- Card H3: Cormorant 24–30px
- Eyebrow label: Jost 11px, letter-spacing 3.5px, uppercase, color sage
- UI / nav: Jost 12px, letter-spacing 1.5px, uppercase
- Body: Jost 15–18px, line-height 1.7, weight 300

### Spacing & Shape
- Content max-width: `1240px`, horizontal padding `40px`.
- Section vertical padding: `~96px` (major), `~74px` (bands).
- Border radius: `2px` (buttons, inputs), `4px` (cards/panels), `6px` (footer logo tile). Deliberately minimal/sharp — editorial feel.
- Grid gaps often rendered as `1px` hairline dividers over a `rgba(58,77,60,0.12)` background (card grids).
- No shadows — the design relies on hairline borders and background tints, not elevation.

---

## Screens / Views

### Global — Header (sticky)
- Sticky top, `background: rgba(247,245,237,0.88)` with `backdrop-filter: blur(12px)`, bottom hairline border.
- Left: **text wordmark** — "IPS" in Cormorant 34px/600 + vertical rule + two-line "INNOVATIVE / PEOPLE SOLUTIONS" in Jost 9.5px, letter-spacing 3px, uppercase, muted. (Note: the client's raster logo is used in the footer, not the header — an earlier header-logo treatment was rejected.)
- Center/right: nav links Home · Services · About · Contact (Jost 12px uppercase). Active link = green `#3a4d3c` with sage bottom-border; inactive = muted `#71766a` transparent border.
- Right: **Book a Consultation** button — green `#3a4d3c` bg, cream text, 2px radius; hover `#2c3a2e`.

### Global — Footer
- Dark green `#2c3a2e` background, `#c3cdba` text.
- 3-column grid (1.4fr / 1fr / 1fr): brand block, Explore links, Contact.
- Brand block: **IPS logo image** (`assets/ips-logo.png`) inside an inline greige `#e0ddd0` tile (radius 6px, 14px padding, logo width 132px), followed by tagline "Your end-to-end HR & Talent partner. People are the strategy."
- Bottom bar (top hairline): copyright left, "HR & Talent, end to end." right.

### 1. Home (`/`)
- **Hero:** 2-col grid (1.05fr / 0.95fr). Left: sage eyebrow "HR & TALENT PARTNERS" with a 34px rule; H1 "People are / the strategy." (Cormorant 76px); subhead paragraph; two CTAs — solid "Book a Consultation" + text link "Explore Services →". Right: **image placeholder** (4/5 aspect, diagonal greige stripe pattern, centered ✦ circle + monospace caption "team / office photo"). *Replace placeholder with a real team/office photo.*
- **Stat strip:** tinted `#f2efe4` band, 3 columns divided by hairlines — "End-to-end / HR & Talent coverage", "Dedicated / partners, not a portal", "Scalable / from startup to scale-up" (Cormorant 46px + uppercase caption).
- **Services preview:** eyebrow "What we do" + H2 "Everything people ops, under one roof." with "All services →" link. 3×2 grid of the first 6 services as hairline-divided cards (numeral, title, one-line blurb). Card hover → `#fdfcf6`.
- **Clients:** dark green `#2c3a2e` band, centered eyebrow "Trusted by teams at", then a wrapped row of 5 client logos, each in a `180×96` cream rounded card (logos object-fit contained).
- **Approach:** 2-col — square striped placeholder ("candid team photo") + eyebrow "Our approach", H2 "A boutique team with enterprise range.", paragraph, "Meet the team →" link.
- **CTA band:** tinted `#f2efe4`, centered H2 "Let's build your people strategy." + paragraph + "Book a Consultation" button.

### 2. Services (`/services`)
- Header block: eyebrow "Services", H1 "End-to-end HR & Talent, tailored to your stage.", intro paragraph.
- **Service grid:** 2-column, hairline-divided cards. Each card = large sage numeral + title (Cormorant 30px) + blurb (see content list below). Hover → `#fdfcf6`.
- Closing dark-green band: "Not sure where to start?" + "Book a Consultation" (cream button on green).

### 3. About (`/about`)
- Intro: 2-col — text (eyebrow "About IPS", H1 "Big-firm expertise, boutique attention.", two paragraphs) + 4/5 striped placeholder ("founder / team portrait").
- **Values:** tinted band, 3 columns — each a numeral + title + blurb (see content).
- **Team:** centered eyebrow "The team" + H2 "Three people, deeply invested." Then a 3-column grid of team members: 150px circular avatar (`#dfe4d8` fill, initials in Cormorant 46px) + name (Cormorant 28px) + role (sage uppercase label) + bio. *Replace initial-avatars with real headshots when available.*

### 4. Contact (`/contact`)
- 2-col layout. Left: eyebrow "Get in touch", H1 "Book a consultation.", paragraph, then Email (`hello@ips-hr.com`) and Phone (`(555) 123-4567`) as Cormorant 24px links. Right: **form panel** — card `#fdfcf6` with hairline border, fields: Name (required), Company, Email (required), "How can we help?" (textarea), "Send Message" submit button.
- On submit: form is replaced by a **success state** — check circle, "Thank you.", confirmation copy.

---

## Content / Copy

### Services (title — blurb), numbered 01–08
1. **HR Advisory & Coaching** — Strategic guidance and leadership coaching that scales alongside your business.
2. **Compliance** — Stay audit-ready with airtight policies, handbooks, and up-to-date regulatory expertise.
3. **Recruiting & Talent** — Attract, assess, and hire the people who move your company forward.
4. **Employee Engagement** — Build a culture people stay for, informed by real feedback and data.
5. **Payroll** — Accurate, on-time payroll without the administrative headache.
6. **Benefits** — Design and manage benefits programs that compete for top talent.
7. **HR Infrastructure** — Systems, processes, and tools that make people operations effortless.
8. **Onboarding & Offboarding** — Seamless transitions that protect your brand and respect your people.

(Home shows services 01–06; Services page shows all 08.)

### Values (About)
1. **Partners, not vendors** — We embed with your leadership and learn the business before we recommend anything.
2. **Senior by default** — You work directly with experienced practitioners — no hand-offs to junior staff.
3. **Built to scale** — Everything we set up is designed to grow with you, from first hire to hundredth.

### Team (placeholder — replace with real names, roles, bios, headshots)
- **Alexandra Moore** — Founder & Principal — "Twenty years across HR strategy, compliance, and total rewards for high-growth companies."
- **Jordan Rivera** — HR Business Partner — "Coaches leaders and builds the people programs that keep teams engaged and growing."
- **Sam Chen** — Talent & Recruiting Lead — "Runs full-cycle recruiting and employer branding that lands standout hires."

> The team names/bios and the contact email/phone are **placeholders** — swap in real values.

---

## Interactions & Behavior
- **Navigation:** header + footer links switch pages; in the prototype this is component state, in production these should be real routes. Every navigation scrolls to top.
- **Hover states:** buttons darken (`#3a4d3c` → `#2c3a2e`); cards lighten to `#fdfcf6`; text links shift green → sage `#8fa389`; nav underline appears on active.
- **Contact form:** client-side; on submit, prevent default and swap the form for a success panel. Wire to a real endpoint / email service (e.g. form handler, CRM) in production. Add real validation (currently only `required` on Name and Email).
- No scroll animations or transitions beyond CSS `transition` on color/background (~0.2s) and smooth scroll.
- **Responsive:** the prototype is built for desktop (2/3-col grids). Add breakpoints — collapse multi-column grids to single column, convert the header nav to a mobile menu, reduce hero H1 size — for tablet/mobile.

## State Management
- Prototype state: `page` (`'home' | 'services' | 'about' | 'contact'`) and `sent` (contact form submitted boolean). In production, replace `page` with router state and `sent` with local form state.

## Assets
Located in `assets/`:
- `ips-logo.png` — IPS monogram + wordmark lockup, **1244×1260**, opaque greige `#e0ddd0` background baked in (no transparency). Used in the footer on a matching greige tile. Client-provided.
- `client-dnam.png`, `client-mhi.jpg`, `client-peak.png`, `client-martie.png`, `client-coco.png` — client logos shown in the Home "Trusted by" strip. Client-provided; varying native backgrounds (e.g. martie has a purple field), displayed on cream cards.
- Image placeholders (striped greige blocks) in the hero and About page mark where **real photography** should go — a team/office photo (hero), candid team photo (Home approach), and founder/team portrait (About).

## Files
- `IPS Website.dc.html` — the complete design reference (all four pages, header, footer). Open in a browser to view. Inline styles throughout; extract into your styling system.
- `assets/` — logo and client/image assets referenced above.
