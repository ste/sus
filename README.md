# sus

Investigation toolkit for researching suspicious companies, corporate networks, and dodgy links between entities. Built on [Claude Code](https://docs.anthropic.com/en/docs/claude-code) with skills, agents, and a Python wrapper around the Companies House API.

## Quick Start

```bash
cd ~/Projects/sus
claude
```

Then ask Claude to investigate:

```
investigate company 12345678
```

Or invoke the spider agent directly:

```
/company-spider 12345678
```

## What's Here

```
.claude/
  skills/
    companies-house/   — How to query the Companies House API via bin/ch
    company-red-flags/ — Red flag patterns for UK company investigations
    investigation-viz/ — Interactive vis.js visualisation generation
  agents/
    company-spider.md  — Recursive company network mapper
bin/
  ch                   — Companies House API wrapper (Python 3, stdlib only)
data/                  — Local investigation data (gitignored)
output/                — Generated reports and visualisations (gitignored)
```

### Skills

Skills are knowledge that Claude loads on demand. They teach Claude *how* to do something without needing to learn it from scratch each session.

- **companies-house** — Documents every `bin/ch` command, response formats, and common investigation patterns
- **company-red-flags** — Catalogue of flags colour-coded by severity (red / orange / yellow) covering shell company indicators, officer patterns, PSC flags, filing anomalies, and network-level flags
- **investigation-viz** — Conventions for generating self-contained HTML visualisations with vis.js (node/edge colours, sidebar layout, companion JSON)

### Agents

Agents are autonomous workflows that Claude runs end-to-end.

- **company-spider** — Given a company number, recursively maps officers, PSCs, and connected companies into a network graph. Applies red flag analysis and generates an interactive visualisation.

### bin/ch

Python script wrapping the [Companies House API](https://developer.company-information.service.gov.uk/). Handles authentication, pagination, URL encoding, rate limit retry, and error handling. Uses only the Python standard library — no pip install needed.

```
bin/ch search "company name"        # Search companies
bin/ch profile 12345678             # Company profile
bin/ch officers 12345678            # All officers
bin/ch pscs 12345678                # Persons with significant control
bin/ch filings 12345678             # Filing history
bin/ch appointments <officer_id>    # Officer's other companies
bin/ch help                         # Full command list
```

## Setup

1. [Install Claude Code](https://docs.anthropic.com/en/docs/claude-code)
2. Get a [Companies House API key](https://developer.company-information.service.gov.uk/)
3. Copy `.env.example` to `.env` and add your key:
   ```
   COMPANIES_HOUSE_API_KEY=your_key_here
   ```

Requires Python 3 (standard on macOS).

## Data

The `data/` and `output/` directories are gitignored. Investigation data stays local. Visualisations are self-contained HTML files in `output/`.
