# iLEARN Wireframing Toolchain

This directory contains all wireframes and design prototypes for the iLEARN platform. We use a four-tool, AI-native wireframing strategy so that AI agents can create and iterate on wireframes automatically alongside human contributors.

---

## Toolchain Overview

| Tool | Purpose | Folder |
|------|---------|--------|
| [Open Design](https://github.com/open-design-systems/open-design) | High-fidelity stakeholder demos using 72 design systems | *(run locally, outputs committed here)* |
| [Draftboard](https://github.com/draftboard/draftboard) | MCP server – AI agents read/write wireframe screens | `draftboard/` |
| [WireMD](https://github.com/wiremd/wiremd) | Version-controlled Markdown wireframes | `wiremd/` |
| [Easy Wireframe](https://github.com/easyWireframe/easyWireframe) | Single-file HTML rapid prototypes with annotation mode | *(generated on demand, not committed)* |

---

## Phase 1 – Stakeholder Demos with Open Design

**What it is:** An AI-native, local-first design engine that bundles 72 brand-grade design systems (Stripe, Miro, Linear, etc.) and drives AI agents (Claude Code, Codex, Cursor, Gemini CLI) to generate polished prototypes.

**How to use:**

```bash
# Install Open Design globally
npm install -g @opendesign/cli

# From this directory, ask your AI agent to generate a prototype
# Example prompt for your AI agent:
# "Using Open Design with the Linear design system, generate a teacher
#  dashboard screen for iLEARN showing: class list, student progress KPIs,
#  and an upcoming session scheduler."
opendesign generate --skill dashboard --design-system linear
```

**License:** Apache-2.0

---

## Phase 2 – AI-Driven Iteration with Draftboard

**What it is:** A local wireframing tool that exposes an MCP (Model Context Protocol) server. AI agents can create, read, update, and delete wireframe screens via the MCP interface. Screens are stored as plain HTML + Markdown files in `draftboard/`.

**How to run:**

```bash
# Install Draftboard
npm install -g draftboard

# Start the Draftboard server (MCP + live preview)
cd wireframes/draftboard
draftboard serve --port 3030

# The MCP endpoint will be at http://localhost:3030/mcp
# Configure your AI agent (e.g. Claude Desktop, Continue.dev) to point to this MCP server
```

**MCP configuration snippet (add to your AI agent config):**

```json
{
  "mcpServers": {
    "draftboard": {
      "url": "http://localhost:3030/mcp"
    }
  }
}
```

**Screens in `draftboard/`:**

- `teacher-dashboard.md` – Teacher home screen with class overview
- `student-learning-path.md` – Student's personalised learning path view
- `progress-tracker.md` – Per-student progress and KPI tracker

---

## Phase 3 – Version-Controlled Wireframes with WireMD

**What it is:** A code-first wireframing tool where UI layouts are written in familiar Markdown syntax. Files live in `wiremd/` and go through the same Git PR/review process as source code.

**How to use:**

```bash
# Install WireMD CLI
npm install -g wiremd

# Render a wireframe to HTML (live preview)
wiremd serve wireframes/wiremd/teacher-dashboard.wiremd

# Export to React/Tailwind
wiremd export wireframes/wiremd/teacher-dashboard.wiremd --format react
```

**Generating wireframes with AI:**

Prompt your AI agent with plain English, e.g.:

> "Generate a WireMD wireframe for a student learning path screen showing: a progress bar at the top, three lesson cards in a row, and a motivational message at the bottom."

The AI will produce a `.wiremd` file you can commit directly.

**Screens in `wiremd/`:**

- `teacher-dashboard.wiremd` – Teacher home screen
- `student-learning-path.wiremd` – Student learning path
- `student-progress-report.wiremd` – Individual student report

---

## Phase 4 – Rapid Prototyping with Easy Wireframe

**What it is:** Generates zero-dependency, single-file HTML wireframes from AI agent prompts. Supports mobile (375×812) and desktop (1440×900) modes, 30+ components, and an annotation mode for stakeholder feedback.

**How to use:**

```bash
# Install Easy Wireframe
npm install -g easy-wireframe

# Generate a desktop wireframe from a prompt
easy-wireframe generate \
  --prompt "Teacher dashboard with class list, three KPI cards for attendance, progress and engagement, and a session scheduler" \
  --mode desktop \
  --output /tmp/teacher-dashboard-proto.html

# Open in browser – stakeholders can annotate directly in the browser
open /tmp/teacher-dashboard-proto.html
```

**Annotation feedback loop:**

1. Export the annotated HTML back from the browser.
2. Feed the annotated HTML to your AI agent.
3. The AI reads the annotations and regenerates a refined wireframe.

> Easy Wireframe outputs are generated on demand and are **not committed** to this repository.

---

## What We Skip (for now)

| Tool | Reason |
|------|--------|
| **WireDSL** | Overlaps with WireMD; revisit if a DSL syntax is preferred over Markdown |
| **Penpot** | Mature Figma alternative but not AI-native; consider when a dedicated design team joins |

---

## Recommended Workflow

1. **New screen needed?** Describe it in plain English → AI generates a `.wiremd` file → commit to `wiremd/`.
2. **Stakeholder demo?** Run Open Design with the appropriate design system to produce a polished prototype.
3. **Rapid exploration?** Use Easy Wireframe locally → annotate → feed annotations back to AI.
4. **Ongoing AI iteration?** Start the Draftboard MCP server → let your AI agent update `draftboard/` screens directly.
