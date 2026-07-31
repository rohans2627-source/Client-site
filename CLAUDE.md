# Project instructions — premium client website builds

You are building a high-end, $5k-quality marketing website. Follow this pipeline for every build.

## Pipeline

1. **Design brief first, always.** Before writing any code, produce a design brief: aesthetic direction (pick one bold direction — editorial, luxury, brutalist, retro-futuristic, cinematic…), a 4–6 value hex palette as CSS variables, 2–3 typefaces (characterful display + refined body, never Inter/Roboto/Arial/system fonts), spacing scale, and a signature motion language (what fades, what reveals on scroll, what the hero does). Save it to `.design/DESIGN_BRIEF.md` and get my approval before building.
2. **Build with the frontend-design skill.** Implement the approved brief exactly. Semantic HTML, CSS variables from the brief, responsive at 375 / 768 / 1440. No generic SaaS card grids, no purple-on-white gradients, no emoji icons.
3. **Components via 21st.dev Magic MCP.** For complex UI (pricing tables, testimonials, navbars, forms), use the magic MCP (`/ui`) and then restyle the output to match the brief's tokens — never ship it with default styling.
4. **Animation via Motion (motion.dev).** Use the motion skill for entrances, scroll reveals, parallax, and hover states. Respect `prefers-reduced-motion`. Motion should reinforce hierarchy, not decorate everything.
5. **Media via Higgsfield MCP.** Generate hero images/videos through the higgsfield MCP. Always tell me the model + credit cost estimate and wait for my confirmation before generating. Match the brief's palette and mood in every prompt.
6. **Review pass.** Before calling it done: check typography consistency, contrast/accessibility, mobile layout, animation performance, and that every section traces back to the design brief.

## Conventions

- Prefer a single-file static HTML/CSS/JS build unless I say otherwise (my clients deploy on simple static hosting).
- Keep images optimized (WebP where possible) and lazy-load below the fold.
- Contact forms via FormSubmit unless the client has a backend.
- Ask before adding paid dependencies or burning generation credits.
