# $5K Website Stack — Claude Code Setup

The 6 tools from the video, with exact install steps. Run these once; steps 1–2 and 4–6 live inside Claude Code, step 3 is a web app.

> **Note for this repo:** the installable pieces are already wired in — see `.mcp.json` (21st.dev Magic + Higgsfield MCPs), `.claude/settings.json` (frontend-design plugin + skills marketplaces), and `.claude/skills/motion-dev-animations` (Motion skill). The steps below are kept as the original reference.

## 0. Start a new project

```bash
mkdir my-new-site && cd my-new-site
claude
```

## 1. Design-brief skill (locks colors, fonts, motion)

Anthropic's official skills marketplace has this covered. Inside Claude Code:

```
/plugin marketplace add anthropics/skills
```

Then browse (`/plugin`) and install the design skills you want — **theme-factory** (complete color palettes + font pairings) is the closest match to "locks in colors and fonts". The frontend-design plugin below also writes a design brief (tokens for color, type, layout, signature motion) as its first pass.

## 2. Frontend Design plugin (turns the brief into code)

```
/plugin marketplace add anthropics/claude-code
/plugin install frontend-design@claude-code-plugins
```

This is Anthropic's official anti-"AI slop" skill: distinctive typography, committed aesthetic direction, intentional motion.

## 3. Claude Design (Anthropic's web app)

Not a Claude Code install — it's a separate Anthropic Labs web app for polished pages and decks. Open claude.ai → Design (or the Claude Design entry point in the app). It builds a design system from your prompt/codebase/images, then every project reuses your colors, typography, and components. Use it to prototype, then bring the direction into Claude Code.

## 4. 21st.dev (Magic MCP — polished components)

1. Get a free API key at 21st.dev's Magic Console.
2. In your terminal:

```bash
claude mcp add magic --scope user --env API_KEY="YOUR_21ST_KEY" -- npx -y @21st-dev/magic@latest
```

Then in Claude Code type `/ui a pricing table with three tiers` etc. Free tier has usage limits.

## 5. Motion.dev skill (fade-ins, scroll reveals, animations)

Motion's official AI Kit installs with one command — copy it from motion.dev/docs/ai-kit-install and it will prompt you to set up Claude Code (project or global). Free, no account needed. Alternative community skill:

```bash
git clone https://github.com/199-biotechnologies/motion-dev-animations-skill.git .claude/skills/motion-dev-animations
```

## 6. Higgsfield MCP (image + video generation)

Needs a Higgsfield account (free signup credits, then paid credits).

Claude Code (terminal):

```bash
claude mcp add --transport http --scope user higgsfield https://mcp.higgsfield.ai/mcp
```

Then run `/mcp` inside Claude Code to complete OAuth sign-in.

Claude app/web (like the video showed): Settings → Connectors → Add custom connector → name it "Higgsfield" → paste `https://mcp.higgsfield.ai/mcp` → Connect.

One connector = 30+ models (Soul, Flux, Kling, Seedance, Veo, Nano Banana, GPT Image, Cinema Studio…).

## Verify

Inside Claude Code:

- `/plugin` — frontend-design shows as installed
- `/mcp` — magic + higgsfield listed and authenticated
- Ask: "What skills do you have available?"

## Workflow (how the video combines them)

1. Write/generate the design brief → colors, fonts, motion locked in
2. frontend-design turns the brief into production code
3. Pull polished sections/components from 21st.dev (`/ui ...`)
4. Layer motion.dev fade-ins, scroll reveals, transitions
5. Generate hero images/videos with Higgsfield
6. Prototype or client-preview polished pages in Claude Design
