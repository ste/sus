---
name: company-red-flags
description: Knowledge base of red flags and suspicious patterns when investigating UK companies. Use when analysing companies, officers, PSCs, or corporate networks for signs of fraud, money laundering, shell companies, or other dodginess.
---

# Company Investigation Red Flags

When investigating companies, look for the following patterns and flag them by colour:

- **Red flag** — serious concern, warrants immediate attention
- **Orange flag** — notable, worth investigating further
- **Yellow flag** — minor concern, note but don't overweight

## Shell Company Indicators

- **Registered at known formation agent addresses** (RED) — e.g., 20-22 Wenlock Road London N1 7GU, 71-75 Shelton Street London WC2H 9JQ, and other high-density registered office addresses. If dozens/hundreds of companies share the same registered address, flag it.
- **No employees reported** in confirmation statements (ORANGE)
- **Dormant accounts filed** since incorporation or for extended periods (ORANGE)
- **Vague SIC codes** (YELLOW-ORANGE) — especially 70229 (Management consultancy), 64209 (Activities of other holding companies), 82990 (Other business support activities)
- **Incorporated shortly before a significant transaction** (RED) — suggests purpose-built vehicle
- **Very low share capital** combined with high-value transactions (ORANGE)

## Officer Red Flags

- **Directors across unusually many companies** (ORANGE-RED) — especially if many are dissolved. Threshold: 10+ active directorships is notable, 20+ is suspicious, 50+ almost certainly a nominee/formation agent
- **Rapid director turnover** (ORANGE) — multiple directors appointed and resigned within short periods
- **Corporate directors** (ORANGE) — companies acting as directors of other companies. Legal but used to obscure beneficial ownership
- **Officers with addresses in secrecy jurisdictions** (RED) — BVI, Cayman Islands, Panama, Seychelles, Marshall Islands, Belize
- **Nominee director patterns** (RED) — same individual as director of many unrelated companies, especially combined with formation agent addresses
- **Recently disqualified directors** still appearing on active companies (RED)

## PSC / Ownership Red Flags

- **PSC chains through offshore entities** (RED) — ownership via BVI, Cayman, Jersey, Guernsey, Isle of Man, Luxembourg, Netherlands (holding companies), Cyprus, Malta
- **Ownership at reporting thresholds** (ORANGE) — "25-50%" brackets suggest structuring to minimise disclosure
- **Multiple layers of corporate ownership** before reaching a natural person (RED)
- **PSC exemptions claimed** without clear justification (ORANGE)
- **No PSC registered** when one should exist (RED) — suggests deliberate concealment

## Filing Pattern Red Flags

- **Late filing penalties** (YELLOW-ORANGE) — one-off may be admin error, repeated is suspicious
- **Accounts overdue** (ORANGE)
- **Sudden changes in accounting reference date** (ORANGE) — can be used to delay disclosure
- **Micro-entity accounts** used to minimise disclosure (YELLOW) — legitimate for small companies but reduces transparency
- **No accounts filed despite trading** (RED)
- **Abbreviated/filleted accounts** with minimal information (YELLOW)

## Network Red Flags (for the spider agent)

- **Circular ownership structures** (RED) — Company A owns Company B which owns Company A
- **Same small group of individuals across many entities** (ORANGE-RED) — especially if companies are in different sectors
- **Shared registered office + shared officers across unrelated sectors** (ORANGE)
- **Dissolved companies that were briefly active** (ORANGE) — incorporated, used briefly, then dissolved
- **Phoenix companies** (RED) — new company formed with same directors/address shortly after previous company dissolved/liquidated
- **Layered structures with no apparent commercial rationale** (RED)

## Investigation Methodology

1. Start with the target company — get profile, officers, PSCs, filing history
2. Map all current and recent officers — check their other directorships
3. Map PSC chain — follow corporate owners to find natural persons
4. Check the registered office — how many other companies use it?
5. Look at the network — shared officers, shared addresses, shared PSCs
6. Check filing patterns — late filings, dormant accounts, micro-entity accounts
7. Cross-reference with known red flags above
8. Score overall suspicion level based on accumulation of flags
9. Generate network visualisation highlighting flagged entities
10. Produce structured report with findings and evidence
