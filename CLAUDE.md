# sus — Investigation Toolkit

This is an investigative toolkit for researching suspicious companies, corporate networks, and links between entities. Primarily focused on UK companies via Companies House, but extensible to other data sources.

## Project Structure

- `.claude/skills/` — Investigation skills (auto-discovered)
- `.claude/agents/` — Autonomous investigation agents
- `data/` — Local investigation data (gitignored, may contain large/sensitive files)
- `output/` — Generated reports, visualisations, diagrams (gitignored)

## Available MCP Tools

- **Companies House** — Search companies, get profiles, officers, PSCs, find links between companies

## Key Conventions

- All visualisations should be self-contained HTML files saved to `output/`
- Use vis.js for interactive network graphs (loaded from CDN)
- Use Mermaid only for simple/small diagrams
- Flag red flags explicitly in output with severity (high/medium/low)
- When investigating, always explain what you're doing and why — this is forensic work, show your reasoning
- Save structured investigation data as JSON in `output/` alongside any visualisations

## Future Integration

- Corpus digger tools for large document analysis (Epstein files, leaked docs, etc.) — to be integrated from existing work
