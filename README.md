# 🔍 sus

Investigation toolkit for researching suspicious companies, corporate networks, and dodgy links between entities.

## Quick Start

```bash
cd ~/Projects/sus
claude
```

Then ask Claude to investigate:

```
investigate company 12345678
```

Or invoke directly:

```
/company-spider 12345678
```

## What's Here

- **Skills** — Investigation knowledge and methodology
  - `company-red-flags` — Red flag patterns for UK company investigations
  - `investigation-viz` — Interactive visualisation generation
- **Agents** — Autonomous investigation workflows
  - `company-spider` — Recursive company network mapper

## Data

The `data/` and `output/` directories are gitignored. Investigation data stays local.

## Requirements

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code)
- Companies House MCP server configured

## Future

- Corpus digger for large document analysis
- Sanctions list cross-referencing
- Address clustering tools
- OSINT enrichment
