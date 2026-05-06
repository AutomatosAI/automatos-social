# Automatos Social Templates

Repeatable post templates designed for the **Automatos AI** platform. Built to be cloned into your Automatos workspace and rendered to PNG by playbooks via a headless browser tool.

## What this is

5 template families × 4 aspect ratios = covers ~95% of educational AI/tech content posts.

| Template     | Use case                                       |
|--------------|------------------------------------------------|
| `title`      | Carousel covers, big single-statement posts    |
| `definition` | "What is X?" — concept explainer w/ 3 cards    |
| `stats`      | By-the-numbers posts, proof-points             |
| `quote`      | Pull-quotes, single-slide inspirational        |
| `announcement` | Product launches, releases, news             |

| Size key    | Dimensions   | Where                              |
|-------------|--------------|------------------------------------|
| `ig_post`   | 1080×1350    | Instagram feed (4:5)               |
| `ig_story`  | 1080×1920    | Instagram Story / Reel (9:16)      |
| `linkedin`  | 1200×628     | LinkedIn / Facebook feed (1.91:1)  |
| `twitter`   | 1600×900     | Twitter/X / YouTube (16:9)         |

## Repo layout

```
.
├── render/
│   ├── index.html              ← Production render entrypoint (URL-param driven)
│   └── _render-shared.js       ← Headless-renderer protocol + helpers
├── templates/
│   ├── _brand.jsx              ← Brand tokens (colors, fonts, atoms)
│   ├── TplTitle.jsx
│   ├── TplDefinition.jsx
│   ├── TplStats.jsx
│   ├── TplQuote.jsx
│   └── TplAnnouncement.jsx
├── schema.json                 ← Field schema per template — agent-readable
├── api-examples.md             ← Sample render calls + Composio integration
├── Automatos Social Templates.html  ← Visual preview / design canvas (devs only)
└── design-canvas.jsx           ← Preview canvas component (devs only)
```

## How rendering works

1. **Playbook generates content** → JSON object of field values
2. **Playbook calls `html-to-png` platform tool** with URL:
   ```
   render/index.html?template=definition&size=ig_post&headline=WHAT%20IS|AN%20AGENT?@brick&card_1=Not%20just%20a%20chatbot|A%20chatbot%20replies.
   ```
3. **Renderer (headless Chrome) opens the URL**, sets viewport to the size's exact dimensions, waits for `document.body[data-render-ready="true"]`, screenshots → PNG bytes
4. **Composio post-to-IG/X/LinkedIn tool** uploads the PNG with the generated caption

The render page is fully static — no API calls, no animation, no auth. Set viewport, navigate, wait for ready flag, screenshot. Done.

## Quick start (local preview)

```bash
# Open the design canvas to see all templates side-by-side
open "Automatos Social Templates.html"

# Preview a single render at production resolution (with field outlines):
open "render/index.html?template=definition&size=ig_post&preview=1"

# Production render (no overlays, ready for screenshot):
open "render/index.html?template=definition&size=ig_post"
```

## Field formats

Three special string formats are used by URL params:

- **`lines`** — pipe-separated headline lines. Suffix `@brick` to color a line in brand orange.
  Example: `WHAT IS|AN AGENT?@brick` → "WHAT IS" in black, "AN AGENT?" in orange
- **`card`** — `Heading|Body` for body cards
  Example: `Not just a chatbot|A chatbot replies. An agent acts.`
- **`stat`** — `Value|Body` for big-number cards
  Example: `5×|Manus rewrote their harness in 6 months.`

Full field reference: see [`schema.json`](./schema.json).

## Brand tokens

Sourced from `frontend/app/globals.css` of the main Automatos repo.

- **Paper bg** `#f1e9dd` (warm cream — social-friendly canvas)
- **Card** `#e3d9c8` · **Ink** `#191919` · **Muted** `#6b6256`
- **Brand orange** `#FF6932` (Dark/Matte `--primary`)
- **Hot orange** `#FF4400` (Light `--primary`, used for hot accents)
- **Display** Inter 900 · **Mono** JetBrains Mono

## Building a new template

1. Create `templates/TplYourThing.jsx` — copy an existing template as a starting point
2. Use `<Field name="your_key">…</Field>` to mark every autofillable region
3. Register the component on `window.TplYourThing`
4. Add a builder in `render/index.html` → `builders.your_thing`
5. Add the template + fields to `schema.json`
6. Add an artboard to `Automatos Social Templates.html` for visual preview
7. Add a sample call to `api-examples.md`

## Sell-through (Automatos Marketplace)

This pack is designed to ship as a Marketplace bundle:

- **Skill** — trains an agent on how to pick a template, fill fields, and call the renderer
- **Playbook** — `daily-social-post.md` that picks one of N weekly facts → generates copy → renders → posts
- **Templates** — this repo, cloned into the user's workspace
- **Platform tool** — `html-to-png` (one-off; reusable for any HTML→PNG job)

See [`api-examples.md`](./api-examples.md) for the canonical playbook flow.
