# Design Brief — Rohan portfolio (v3: Studio Noir)

Direction pivot per client: no cultural theming. **Professional, modern, cinematic —
a high-end digital studio aesthetic where motion is the signature.**

- **Subject:** a solo web developer in Accra selling premium builds to business owners
- **The page's single job:** get them to open WhatsApp or email
- **Personality:** confident, precise, expensive. The animations do the talking.

## Aesthetic direction

**Studio noir.** Near-black ink ground, soft-white type, one hot accent used sparingly
(signal orange), and mono-spaced technical labels. Generous space, big type, rounded
surfaces. No gradients-on-white, no SaaS card grids — hierarchy comes from scale and
motion.

## Palette (CSS variables)

```css
--ink:    #0A0A0B;  /* ground */
--panel:  #131316;  /* raised cards */
--line:   rgba(245,245,243,.09);
--white:  #F5F5F3;  /* primary text */
--grey:   #8B8B94;  /* secondary text */
--accent: #FF4D00;  /* signal orange — CTAs, highlights, cursor */
```

## Typography (3 families)

- **Display: Syne** 700/800 — geometric, contemporary, slightly odd; huge headlines,
  tight leading (0.95), -0.03em tracking.
- **Body: Manrope** 400/500/600 — clean, professional prose.
- **Technical: JetBrains Mono** — eyebrows, stats, numbers, the preloader counter.
  Mono labels get a scramble-decode animation on reveal.

## Signature: the motion system

- **Preloader:** giant mono counter 000→100, then the curtain wipes up.
- **Kinetic hero:** headline lines launch up with skew; an endless band of giant
  outlined text scrolls behind the fold; a soft orange aurora drifts in the dark.
- **Sticky-stack work:** each project is a full card that pins while the next one
  slides over it — the covered card scales down and dims (the "deck of work" moment).
- **Scramble labels:** mono eyebrows decode from random glyphs when they enter view.
- **Custom cursor:** difference-blend dot + lagging ring; ring flares on links.
- **Magnetic CTAs**, count-up stats, 3D-tilt browser mockups, client ticker,
  nav that hides on scroll-down and returns on scroll-up.
- All of it collapses to static under `prefers-reduced-motion`; touch devices skip
  cursor/magnetic/tilt.

## Layout

Nav → hero (kinetic type + aurora + outlined marquee) → client ticker →
Selected Work 01–05 (sticky stack) → Services (4 hover-glow cards) → CTA (giant
headline, WhatsApp/email) → footer (live GMT clock).

## Content

All real content carries over: five projects with tech pills, features, stats, live
links; four services; WhatsApp +233 55 675 7128 and email. Location stays as a fact
("Accra, GH" in the eyebrow and footer) — it's just no longer the theme.
