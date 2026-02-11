# sus — Investigation Toolkit

Investigative toolkit for researching suspicious UK companies, corporate networks, and links between entities.

## Project Structure

- `bin/ch` — Companies House API wrapper script (curl + jq, no other dependencies)
- `.claude/skills/` — Skills (auto-discovered by Claude Code)
  - `companies-house/` — API query reference for `bin/ch`
  - `company-red-flags/` — Flag patterns (red / orange / yellow)
  - `investigation-viz/` — vis.js visualisation conventions
- `.claude/agents/` — Autonomous investigation agents
  - `company-spider.md` — Recursive company network mapper
- `data/` — Local investigation data (gitignored)
- `output/` — Generated reports, visualisations, JSON (gitignored)
- `.env` — API key storage (gitignored)

## Companies House API

- Query with `bin/ch <command>` — see the `companies-house` skill for full docs
- API key stored in `.env` as `COMPANIES_HOUSE_API_KEY=...`
- The script handles auth, pagination, and error handling via curl + jq
- Run `bin/ch help` for the full command list

## Key Conventions

- All visualisations are self-contained HTML files saved to `output/`
- Use vis.js for interactive network graphs (loaded from CDN)
- Save structured investigation data as JSON in `output/` alongside visualisations
- Flag issues by colour: red (serious), orange (notable), yellow (minor)
- When investigating, explain what you're doing and why — this is forensic work, show your reasoning
