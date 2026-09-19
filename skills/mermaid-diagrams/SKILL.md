---
name: mermaid-diagrams
description: Render architecture diagrams, flowcharts, sequence charts, and visual mindmaps into clean SVG or PNG images using the doc-diagram-renderer MCP tools.
tools:
  - doc-diagram-renderer
---

# Mermaid Diagram Renderer Skill

This skill allows agents to generate high-quality visual diagrams (architecture, sequence flows, ERDs, mindmaps, state machines) using Mermaid.js via the `doc-diagram-renderer` MCP service.

## When to Use

Use this skill whenever the user asks for:
- System architectures or infrastructure diagrams
- Process workflows, step-by-step logic flows, or state diagrams
- Sequence diagrams explaining API interactions or protocols
- Entity-Relationship diagrams (database schemas)
- Visual roadmaps or Gantt charts

## Available MCP Tools

From the `doc-diagram-renderer` connector:
- `render_mermaid`: Compiles Mermaid syntax into SVG or PNG format.

### Parameters
- `syntax` (string, required): Valid Mermaid diagram definition (e.g. starting with `flowchart TD`, `sequenceDiagram`, `erDiagram`, etc.).
- `output_format` (string, optional): `"svg"` (default) or `"png"`. SVG is strongly recommended for vector sharpness and small payload size.
- `theme` (string, optional): `"default"`, `"neutral"`, `"dark"`, or `"forest"`.

## Best Practices & Guidelines

1. **Syntax Cleanliness**:
   - Ensure node IDs do not contain spaces or special characters (e.g., use `apiGateway["API Gateway (Port 8080)"]` instead of raw spaces in ID).
   - Use direction hints like `TD` (Top-Down) or `LR` (Left-to-Right) appropriately to keep charts legible.
2. **Clarity over Complexity**:
   - Group related components into subgraphs for complex architectures.
   - Use clear labels on edges to describe the interaction or data flow.
3. **Delivery**:
   - Return the rendered diagram link/path and provide a concise textual explanation of the diagram components.
