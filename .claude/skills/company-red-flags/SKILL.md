---
name: company-red-flags
description: Knowledge base of red flags and suspicious patterns when investigating UK companies. Use when analysing companies, officers, PSCs, or corporate networks for signs of fraud, money laundering, shell companies, or other dodginess.
---

# Company Investigation Red Flags

When investigating companies, look for the following patterns and flag them with severity levels (HIGH / MEDIUM / LOW).

## Shell Company Indicators

- **Registered at known formation agent addresses** (HIGH) — e.g., 20-22 Wenlock Road London N1 7GU, 71-75 Shelton Street London WC2H 9JQ, and other high-density registered office addresses. If dozens/hundreds of companies share the same registered address, flag it.
- **No employees reported** in confirmation statements (MEDIUM)
- **Dormant accounts filed** since incorporation or for extended periods (MEDIUM)
- **Vague SIC codes** (LOW-MEDIUM) — especially 70229 (Management consultancy), 64209 (Activities of other holding companies), 82990 (Other business support activities)
- **Incorporated shortly before a significant transaction** (HIGH) — suggests purpose-built vehicle
- **Very low share capital** combined with high-value transactions (MEDIUM)

## Officer Red Flags

- **Directors across unusually many companies** (MEDIUM-HIGH) — especially if many are dissolved. Threshold: 10+ active directorships is notable, 20+ is suspicious, 50+ almost certainly a nominee/formation agent
- **Rapid director turnover** (MEDIUM) — multiple directors appointed and resigned within short periods
- **Corporate directors** (MEDIUM) — companies acting as directors of other companies. Legal but used to obscure beneficial ownership
- **Officers with addresses in secrecy jurisdictions** (HIGH) — BVI, Cayman Islands, Panama, Seychelles, Marshall Islands, Belize
- **Nominee director patterns** (HIGH) — same individual as director of many unrelated companies, especially combined with formation agent addresses
- **Recently disqualified directors** still appearing on active companies (HIGH)

## PSC / Ownership Red Flags

- **PSC chains through offshore entities** (HIGH) — ownership via BVI, Cayman, Jersey, Guernsey, Isle of Man, Luxembourg, Netherlands (holding companies), Cyprus, Malta
- **Ownership at reporting thresholds** (MEDIUM) — "25-50%" brackets suggest structuring to minimise disclosure
- **Multiple layers of corporate ownership** before reaching a natural person (HIGH)
- **PSC exemptions claimed** without clear justification (MEDIUM)
- **No PSC registered** when one should exist (HIGH) — suggests deliberate concealment

## Filing Pattern Red Flags

- **Late filing penalties** (LOW-MEDIUM) — one-off may be admin error, repeated is suspicious
- **Accounts overdue** (MEDIUM)
- **Sudden changes in accounting reference date** (MEDIUM) — can be used to delay disclosure
- **Micro-entity accounts** used to minimise disclosure (LOW) — legitimate for small companies but reduces transparency
- **No accounts filed despite trading** (HIGH)
- **Abbreviated/filleted accounts** with minimal information (LOW)

## Network Red Flags (for the spider agent)

- **Circular ownership structures** (HIGH) — Company A owns Company B which owns Company A
- **Same small group of individuals across many entities** (MEDIUM-HIGH) — especially if companies are in different sectors
- **Shared registered office + shared officers across unrelated sectors** (MEDIUM)
- **Dissolved companies that were briefly active** (MEDIUM) — incorporated, used briefly, then dissolved
- **Phoenix companies** (HIGH) — new company formed with same directors/address shortly after previous company dissolved/liquidated
- **Layered structures with no apparent commercial rationale** (HIGH)

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
