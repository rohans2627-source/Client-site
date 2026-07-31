# Design Brief — Rohan portfolio redesign

## Concept: Ananse's Loom

In Akan folklore, Ananse the spider is the keeper of stories and the weaver of webs.
Rohan builds websites in Accra — he is, literally, a web-weaver. The redesign treats the
portfolio as woven cloth: kente is woven in narrow strips sewn together, so the page is
composed as **strips** — a woven selvedge band at the top of the page, project rows that
read as strips of cloth, and thread-colored seams marking each project. The old site's
generic "European luxury noir + gold" is replaced by something only this person in this
city could own.

- **Subject:** a solo web developer/craftsman in Accra selling premium builds to Ghanaian businesses
- **Audience:** Ghanaian business owners deciding whether to commission a website
- **The page's single job:** get them to open WhatsApp or email

## Aesthetic direction

**Woven modernism.** Deep indigo-dyed ground (night cloth, not pure black), undyed-cotton
ivory for text, and three thread colors from the kente loom — gold, scarlet, forest —
used as structural seams, never as decoration. Flat, precise, zero border-radius on
structure; the warmth comes from color and type, not softness.

## Palette (CSS variables)

```css
--indigo:   #191B2C;  /* ground — indigo-dyed night cloth */
--indigo-2: #212439;  /* raised surface / cards */
--cloth:    #EFE7D2;  /* undyed cotton — primary text */
--thread-g: #E0A32E;  /* kente gold — primary accent, links, CTAs */
--thread-r: #C7482F;  /* scarlet thread — secondary seam */
--thread-f: #3E8A63;  /* forest thread — tertiary seam */
--mist:     #9B98AC;  /* muted text on indigo */
```

Each of the five projects is assigned a seam color (rotating gold → scarlet → forest),
so the work section reads as sewn strips of different cloths.

## Typography (2 families)

- **Display: Bricolage Grotesque** (800/600) — chunky, warm, contemporary; carries the
  headlines and the big numerals. Tight leading (0.95), slight negative tracking.
- **Body: Newsreader** (400/500 + italics) — a refined text serif for prose and the
  storytelling asides. Italic used for the Ananse aside and project subtitles.
- Labels/eyebrows: Bricolage Grotesque 600 at 11px, letter-spaced caps (no third family).

Type scale: 12 / 15 / 18 / 24 / 34 / clamp(44→96) display.

## Spacing scale

4 / 8 / 16 / 24 / 40 / 64 / 104 / 160. Section padding 160px desktop, 88px mobile.
Content column max 1200px; text measure max 560px.

## Signature element

**The loom band + Ananse's web.** A five-strip woven band runs across the very top of
the page (the selvedge), whose strips draw in on load like threads pulled across a loom.
The hero carries a hand-drawn Ananse Ntontan (spider's-web Adinkra symbol — wisdom,
craft) as an SVG that draws itself, with a one-line italic aside explaining it. Every
section seam re-uses the thread motif: project rows open with a colored seam that
stitches across on scroll.

## Motion language

- **Load:** loom band strips scale in left→right (staggered); web mark strokes draw; hero
  lines rise with a clip-path wipe (cloth unrolling), not blur/fade.
- **Scroll:** section seams stitch across (scaleX); content reveals with a short
  translate + clip wipe; browser mockups get one sheen pass.
- **Ticker:** a thin marquee strip of the five client names runs between hero and work,
  in loom colors.
- **Hover:** links underline with a dashed→solid "stitch"; CTAs fill with thread gold;
  mockup plates keep a restrained 3D tilt (pointer:fine only).
- `prefers-reduced-motion`: all of the above collapse to static, fully-visible states.

## Interaction layer (final build)

- **Preloader:** ~1s loom curtain — five thread columns descend, then the whole
  overlay lifts to reveal the hero sequence. Skipped entirely under reduced motion.
- **Custom cursor:** gold thread-dot with a lerped ring that expands over any link
  or button. Pointer-fine devices only.
- **Magnetic buttons:** CTAs lean toward the cursor and spring back on leave.
- **Scroll progress:** a 2px gold thread under the loom band tracks reading position.
- **Ananse's web:** ambient 90s rotation plus a soft mouse parallax in the hero.
- **Count-up stats:** each strip's "under the hood" numbers count up when the strip
  reveals.
- **Mobile menu:** full-screen indigo overlay with oversized Bricolage links and both
  contact CTAs; burger morphs to X, Escape closes, body scroll locks.
- **Woven texture:** a 3% opacity thread-grid overlays the whole page.
- **Footer clock:** live Accra (GMT) time — a studio signature.

## What carries over from the old site

All real content: the five projects (Atlantic Catering, Glimmer Jewels, K's Korner,
Bab Photography, Walk a Wheel) with their tech pills, key features, stats and live
links; the four services; WhatsApp (+233 55 675 7128) and email CTAs. The deck/slideshow
is replaced by a scroll editorial — better on mobile, where his clients actually are.
