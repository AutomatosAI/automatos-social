# Automatos Weekly Social Facts
#
# FORMAT RULES (agents MUST follow these exactly):
#
# Headline grammar:
#   - 2–4 lines, separated by `|`
#   - ALL CAPS, max ~10 chars per line
#   - Optional `@brick` suffix to color a line orange
#   - NO long words (>10 chars) — they overflow at Inter Black 100–170px
#
# Card grammar:
#   - `Heading|Body` — heading ≤ 28 chars, body ≤ 160 chars
#
# Stat grammar:
#   - `Value|Body` — value ≤ 4 chars (e.g. "10+", "95%"), body ≤ 60 chars
#
# CAROUSEL STRUCTURE:
#   Each day has a `slides` array with 3–5 slides.
#   Slide 1 is always a `title` template (the hook/cover).
#   Remaining slides use definition, stats, quote, or announcement.
#   The `page` and `total` fields are auto-set by the renderer.

- week_start: 2026-05-04
- owner: SOCIAL OPS
- consumer_playbook: Automatos Instagram Carousel - Daily Fact Post
- path: content/social/weekly-facts.md

---

- id: 2026-w19-tue
  day: Tuesday
  topic: Agents
  slides:
    - template: title
      fields:
        eyebrow: AI AGENTS 101
        headline: WHAT IS|AN@brick|AGENT?
        subline: Not just a chatbot. An agent plans, acts, observes, and loops — autonomously driving toward a goal.
        cta: Swipe to learn →

    - template: definition
      fields:
        eyebrow: THE BASICS
        headline: AGENTS|ARE@brick|DIFFERENT.
        card_1: Roles, not prompts|Each agent ships with a scoped role, permissions, and a skill graph.
        card_2: Tools, not tokens|Agents call APIs, read files, write code — not just generate text.
        card_3: Loops, not turns|Plan → act → observe → repeat until the goal is met.
        cta: What makes them work →

    - template: stats
      fields:
        eyebrow: BY THE NUMBERS
        headline: AGENTS|AT@brick|SCALE.
        stat_1: 109|Tables powering agent state
        stat_2: 30+|Skills per agent
        stat_3: 10×|Loop iterations per task
        card_1: Production-grade|Not a demo — running real workloads in production today.
        card_2: Skill routing|Tasks matched to agents by skill graph, not keyword.
        cta: See the architecture →

    - template: quote
      fields:
        eyebrow: THE PRINCIPLE
        quote: The model is the brain. The harness is everything else.
        accent: harness
        attribution: Automatos · core design principle
        cta: Save this →

---

- id: 2026-w19-wed
  day: Wednesday
  topic: Playbooks
  slides:
    - template: title
      fields:
        eyebrow: AUTOMATION
        headline: WHAT IS|A@brick|PLAYBOOK?
        subline: An ordered graph of agent steps. Reads like a recipe, runs like a CI job. Repeatable by default.
        cta: Swipe to learn →

    - template: definition
      fields:
        eyebrow: HOW IT WORKS
        headline: STEPS.|AGENTS.|DONE.@brick
        card_1: Sequenced steps|Each step activates an agent with a scoped prompt and tool set.
        card_2: Multi-agent handoff|Context routes between agents automatically — no glue code.
        card_3: Deterministic|Same input, same output. Randomness is opt-in, not default.
        cta: Inside a playbook →

    - template: stats
      fields:
        eyebrow: PLAYBOOK METRICS
        headline: RUN|ONCE.@brick|RUN|FOREVER.
        stat_1: 3|Steps in our social post playbook
        stat_2: 0|Manual touches per run
        stat_3: 24/7|Scheduled or on-demand
        card_1: Self-healing|Retries and fallbacks built into the execution engine.
        card_2: Observable|Every step logged, timed, and auditable.
        cta: Build your first →

    - template: quote
      fields:
        eyebrow: FIELD NOTES
        quote: If you have to explain the process twice, it should be a playbook.
        accent: playbook
        attribution: Automatos · operating principle
        cta: Save this →

---

- id: 2026-w19-thu
  day: Thursday
  topic: Workspace
  slides:
    - template: title
      fields:
        eyebrow: YOUR AI WORKSPACE
        headline: ONE|PLACE.@brick|EVERY|TOOL.
        subline: Code, docs, data, integrations — all in one workspace. Agents share it. You control it.
        cta: Swipe to explore →

    - template: definition
      fields:
        eyebrow: INSIDE THE WORKSPACE
        headline: FILES.|TOOLS.|STATE.@brick
        card_1: Read & write|Agents create, edit, and organize workspace files like a human would.
        card_2: Scoped access|Each agent sees only what its role permits. No data leaks.
        card_3: Persistent state|Workspace survives sessions. Pick up where you left off.
        cta: What's inside →

    - template: stats
      fields:
        eyebrow: WORKSPACE POWER
        headline: THE|WORKSPACE.@brick|EVERYTHING|CONNECTED.
        stat_1: 10+|Built-in tools on day one
        stat_2: 5+|File types parsed natively
        stat_3: 20+|Third-party integrations
        card_1: Code & docs|Edit, search, refactor across repos and notebooks.
        card_2: Data & APIs|Postgres, Snowflake, Slack, Linear — one auth, one config.
        cta: Tour the workspace →

---

- id: 2026-w19-fri
  day: Friday
  topic: Routing
  slides:
    - template: title
      fields:
        eyebrow: INTELLIGENCE LAYER
        headline: SMART|ROUTING.@brick|RIGHT|AGENT.
        subline: Every task scored against every agent's skill graph. The best match wins — in milliseconds.
        cta: Swipe for details →

    - template: stats
      fields:
        eyebrow: ROUTING PERFORMANCE
        headline: FAST.|ACCURATE.|SMART.@brick
        stat_1: 95%|Task-routing accuracy
        stat_2: <1s|Route decision time
        stat_3: 30+|Skills scored per route
        card_1: Semantic matching|Not keyword lookup — embeddings match intent to capability.
        card_2: Load-aware|Hot agents shed work to available replicas automatically.
        cta: How it works →

    - template: definition
      fields:
        eyebrow: THE ROUTER
        headline: NO|GUESSING.@brick|JUST|MATCHING.
        card_1: Skill graphs|Every agent declares what it can do. The router reads the graph.
        card_2: Intent scoring|Your request is embedded and scored against all available skills.
        card_3: Fallback chains|If the best agent is busy, the next-best picks up instantly.
        cta: See routing in action →

---

- id: 2026-w19-sat
  day: Saturday
  topic: Renderer
  slides:
    - template: title
      fields:
        eyebrow: CONTENT ENGINE
        headline: HTML|→ PNG.@brick|NO CANVA.|NO FIGMA.
        subline: Parameterized HTML templates. Headless Chromium renders them to pixel-perfect PNGs. Version-controlled. Code-reviewed.
        cta: Swipe to see how →

    - template: definition
      fields:
        eyebrow: THE PIPELINE
        headline: TEMPLATE.|RENDER.|POST.@brick
        card_1: HTML templates|Every post is a parameterized page — diff it, PR it, deploy it.
        card_2: Headless render|Playwright screenshots at exact dimensions. No manual export.
        card_3: Auto-publish|Playbook chains: generate → render → caption → post. Hands-free.
        cta: Inside the pipeline →

    - template: announcement
      fields:
        status: LIVE
        eyebrow: SHIPPING NOW
        headline: THIS|POST@brick|WAS|RENDERED.
        subline: You're looking at it. This carousel was generated, rendered, and posted by an Automatos playbook.
        feature_1: 5 templates|Title, definition, stats, quote, announcement — all parameterized.
        feature_2: 4 sizes|Instagram, Stories, LinkedIn, Twitter — one template, any canvas.
        feature_3: Zero manual steps|From content → image → Instagram in one playbook run.
        cta: Try it yourself →

---

- id: 2026-w19-sun
  day: Sunday
  topic: Platform Overview
  slides:
    - template: title
      fields:
        eyebrow: THE FULL PICTURE
        headline: THIS IS|AUTOMATOS.@brick
        subline: Agents. Playbooks. Workspace. Routing. Skills. One platform for AI-powered operations.
        cta: Swipe for the summary →

    - template: quote
      fields:
        eyebrow: THE VISION
        quote: Build the harness once. Run any model. Ship any workflow.
        accent: harness once
        attribution: Automatos · founding principle
        cta: Follow for more →
