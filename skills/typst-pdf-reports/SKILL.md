---
name: typst-pdf-reports
description: Design and compile publication-grade, beautifully formatted PDF documents, whitepapers, invoices, and technical reports using Typst via doc-diagram-renderer.
tools:
  - doc-diagram-renderer
---

# Typst PDF Reports Skill

This skill empowers agents to produce publication-grade, modern PDF documents using Typst via the `doc-diagram-renderer` MCP tool. Typst provides LaTeX-level typesetting quality with lightning-fast compilation and elegant modern styling.

## When to Use

Use this skill when the user requests:
- Formal business reports, executive summaries, or whitepapers
- Invoices, quotes, or branded company documentation
- Technical documentation, research papers, or mathematical summaries
- Printable cheatsheets, guidelines, or structured manuals

## Available MCP Tools

From the `doc-diagram-renderer` connector:
- `compile_typst`: Compiles Typst source code into a downloadable PDF document.

### Parameters
- `source` (string, required): The complete Typst markup code (`.typ` syntax).
- `filename` (string, optional): Desired filename for the resulting PDF (e.g. `quarterly-report.pdf`).

## Typst Syntax Quick Reference

```typst
#set page(paper: "a4", margin: (x: 2cm, y: 2.5cm))
#set text(font: "Liberation Sans", size: 11pt, lang: "en")

#align(center)[
  #text(20pt, weight: "bold")[Technical Architecture & Evaluation Report] \
  #text(12pt, fill: luma(100))[Prepared for Enterprise Deployment] \
  #datetime.today().display()
]

#v(1.5cm)

= Executive Summary
This document outlines the performance benchmarks and architectural decisions.

== Key Findings
- 40% reduction in processing latency
- Zero data loss during failover testing

#table(
  columns: (1fr, 2fr, 1fr),
  align: (left, left, center),
  [*Metric*], [*Description*], [*Result*],
  [Throughput], [Concurrent requests per second], [14,500 req/s],
  [P99 Latency], [99th percentile response time], [42 ms],
)
```

## Best Practices & Guidelines

1. **Clean Layout**:
   - Always specify page margins and paper size (`a4` or `us-letter`).
   - Use `#align`, `#columns`, and `#table` to create visually appealing layouts.
2. **Typography**:
   - Use headings (`=`, `==`, `===`) consistently.
   - Use accent colors sparingly for headers or highlight callouts.
3. **Data Display**:
   - Prefer structured Typst `#table(...)` definitions for data comparison rather than plain bullet lists.
