# Agentic Research Loop — Session 0 Demo

A single-file, self-contained dashboard that walks through an agentic research loop step by step:
**Meta Orchestrator → Research Agent → Haiku sub-agent → MCP tools → Information DB → Assumptions Invalidator → loop → exit.**

Click **Next →** to advance through 17 steps. Each step shows the active agent's prompt, thinking, tools, MCP request/response, and a tutorial concept callout.

## View the demo

Just open `index.html` in a browser. No server required.

## Share with others (three options)

### Option 1 — GitHub Pages (recommended, clean URL)

```bash
# From any folder:
mkdir agentic-demo && cd agentic-demo
cp /path/to/this/index.html .
git init && git add index.html
git commit -m "Session 0 dashboard"
gh repo create agentic-demo --public --source=. --push
```

Then in the repo on github.com: **Settings → Pages → Source: `main` branch, `/ (root)` → Save**.
Your demo lives at `https://<username>.github.io/agentic-demo/` within a minute.

### Option 2 — raw.githack.com (no Pages config needed)

Push `index.html` to any repo, then share:
`https://raw.githack.com/<username>/<repo>/main/index.html`

### Option 3 — GitHub Gist

```bash
gh gist create index.html --public --desc "Agentic research loop demo"
```

Use the gist URL with `https://htmlpreview.github.io/?<gist-raw-url>` to render.

## Local development

```bash
# Just a browser — no server
open index.html

# OR with the optional server.py for skill-driven advancement
python3 server.py     # serves on :8888, adds /advance and /reset endpoints
```

## What it demonstrates

- **Orchestrator pattern** — a manager agent that only spawns, never executes
- **Sub-agent spawning** — isolated contexts with their own prompts and tools
- **Model tiering** — Opus for reasoning, Haiku for retrieval (~20× cheaper)
- **Least privilege** — read-only tools for retrieval sub-agents
- **MCP (Model Context Protocol)** — how tools are declared, routed, executed
- **Structured memory** — an Information DB with a parent-defined schema
- **Producer + critic** — a separate Assumptions Invalidator finds gaps
- **Bounded iteration** — loop guard (max 5) with human escalation fallback
- **Context handoff** — DB as the interface between research and build phases
