---
name: investigation-viz
description: Instructions for rendering investigation results as interactive visualisations. Use when generating network diagrams, relationship maps, or investigation reports that need visual output.
---

# Investigation Visualisation

## Output Location

All visualisations go to the `output/` directory as self-contained HTML files.

## Technology Choice

- **Interactive HTML with vis.js** — default for network/relationship diagrams. Use vis.js loaded from CDN (https://unpkg.com/vis-network/standalone/umd/vis-network.min.js)
- **Mermaid** — only for simple diagrams with fewer than ~15 nodes
- Never use images or screenshots — always interactive

## Network Graph Conventions

### Node Types (colour-coded)
- **Target company** — red, larger node
- **Related companies (active)** — blue
- **Related companies (dissolved)** — grey
- **Natural persons** — green circles
- **Corporate entities (PSCs/parent companies)** — orange diamonds
- **Offshore entities** — yellow with red border

### Edge Types
- **Director of** — solid blue arrow
- **Secretary of** — dashed blue arrow
- **PSC / significant control** — solid red arrow (with ownership % as label)
- **Registered office match** — dotted grey line

### Flag Indicators
- Nodes with flags get a coloured glow/border matching severity (red / orange / yellow)
- Tooltip on hover shows the specific flags
- A summary panel lists all flags found with colour

## HTML Template Requirements

- Self-contained single HTML file (no external dependencies except CDN)
- Include a title and timestamp
- Include a sidebar or panel with:
  - Investigation summary
  - List of all entities found
  - Flags with colour (red / orange / yellow)
  - Clickable list that highlights nodes in the graph
- Graph should be zoomable and pannable
- Clicking a node shows its details
- Include a search/filter box
- Export button to save the graph data as JSON

## Companion Data

Always save the raw investigation data as a JSON file alongside the HTML:
- `output/{investigation-name}.html` — the visualisation
- `output/{investigation-name}.json` — structured data

## JSON Structure

```json
{
  "investigation": {
    "target": "company number or name",
    "date": "ISO date",
    "depth": 2
  },
  "entities": {
    "companies": [...],
    "persons": [...]
  },
  "relationships": [...],
  "red_flags": [
    {
      "entity": "...",
      "flag": "...",
      "severity": "RED|ORANGE|YELLOW",
      "evidence": "..."
    }
  ]
}
```
