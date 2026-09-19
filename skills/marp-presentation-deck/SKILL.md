---
name: marp-presentation-deck
description: Create modern slide decks, pitch presentations, and lecture slides in Markdown and render them to HTML or PDF using Marp via doc-diagram-renderer.
tools:
  - doc-diagram-renderer
---

# Marp Presentation Deck Skill

This skill enables agents to generate structured presentation slide decks using Marp (Markdown Presentation Ecosystem) via the `doc-diagram-renderer` MCP service.

## When to Use

Use this skill when the user asks for:
- Pitch decks, conference talks, or workshop slides
- Training presentations or internal team briefings
- Executive slide summaries or project status decks

## Available MCP Tools

From the `doc-diagram-renderer` connector:
- `create_marp_slides`: Renders Markdown slides using Marp into HTML slides or PDF decks.

### Parameters
- `markdown` (string, required): Marp-formatted Markdown slide definitions.
- `output_format` (string, optional): `"html"` (interactive web presentation) or `"pdf"` (printable deck).
- `theme` (string, optional): `"default"`, `"gaia"`, or `"uncover"`.

## Marp Markdown Structure

Marp decks begin with frontmatter (`marp: true`) and delimit slides using `---`:

```markdown
---
marp: true
theme: gaia
_class: lead
paginate: true
backgroundColor: #f5f5f5
---

# Modern Agent Workflows
## Scaling Intelligent Systems locally

Presenter: AI Assistant
Date: 2026

---

# Architecture Overview

- **Local MCP Gateway**: Unified protocol for tools & connectors
- **Isolated Sandbox**: Docker-based execution runtime
- **State Management**: PostgreSQL & Vector Store integration

---

<!-- _footer: "Confidential - Internal Use Only" -->

# Performance Benchmarks

| Metric | Target | Result |
| :--- | :--- | :--- |
| Agent Spin-up | < 2s | 1.1s |
| Tool Invocation | < 50ms | 18ms |
| Memory Overhead | < 256MB | 140MB |

---

# Next Steps & Roadmap

1. Complete automated regression suite
2. Enable custom skills self-registry
3. Expand local embedding capabilities
```

## Best Practices

1. **Slide Brevity**: Keep bullet points concise (max 4-5 points per slide). Avoid wall-of-text slides.
2. **Slide Dividers**: Separate every single slide with `---`.
3. **Visual Structure**: Use tables, bold highlights, and subheadings to guide audience attention.
