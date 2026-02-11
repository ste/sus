---
name: companies-house
description: How to query the Companies House API using the bin/ch wrapper script. Use this whenever you need to look up UK company data — profiles, officers, PSCs, filings, charges, insolvency, officer appointments, and searches.
---

# Companies House API

Query UK company data using the `bin/ch` wrapper script. This handles authentication, pagination, and error handling. All output is JSON.

## Prerequisites

- API key must be set in `.env` as `COMPANIES_HOUSE_API_KEY=...`
- The script uses curl and jq (both available on this system)

## Commands

Run from the project root. All commands return JSON.

### Search for companies

```bash
bin/ch search "company name or partial number"
```

Returns up to 20 results with company_number, title, company_status, date_of_creation, registered_office_address, etc.

### Get company profile

```bash
bin/ch profile 12345678
```

Returns full company details: name, status, type, SIC codes, registered office, accounts info, confirmation statement dates, etc.

### List officers

```bash
bin/ch officers 12345678           # all officers (current + resigned)
bin/ch officers 12345678 current   # current officers only
```

Returns all officers with auto-pagination. Each officer includes: name, officer_role, appointed_on, resigned_on, nationality, occupation, address, and crucially `links.officer.appointments` which contains the **officer_id** needed for the `appointments` command.

**Extracting officer_id**: The officer_id is embedded in the appointments link. For example, if `links.officer.appointments` is `/officers/abc123def/appointments`, the officer_id is `abc123def`.

### List PSCs (Persons with Significant Control)

```bash
bin/ch pscs 12345678
```

Returns PSCs with: name, natures_of_control (ownership %), nationality, country_of_residence, address, and for corporate PSCs: identification details.

### Get filing history

```bash
bin/ch filings 12345678                    # recent filings (50 most recent)
bin/ch filings 12345678 accounts           # only accounts filings
bin/ch filings 12345678 confirmation-statement
```

Categories: accounts, annual-return, capital, change-of-name, confirmation-statement, incorporation, liquidation, mortgage, officers, resolution, persons-with-significant-control.

### Get charges/mortgages

```bash
bin/ch charges 12345678
```

### Get insolvency info

```bash
bin/ch insolvency 12345678
```

### Get officer's other appointments

```bash
bin/ch appointments <officer_id>
```

This is the key command for network mapping — it shows every company an officer is or was connected to. Returns: company name, company number, company status, officer role, appointed/resigned dates.

### Search for officers by name

```bash
bin/ch search-officers "John Smith"
```

### Search disqualified officers

```bash
bin/ch search-disqualified "John Smith"
```

### Get registered office address

```bash
bin/ch registered-office 12345678
```

## Rate Limits

The Companies House API has a rate limit of 600 requests per 5 minutes. The script will return a rate_limited error if you hit it — wait a few seconds and retry.

## Common Investigation Patterns

### Map a company's network

```bash
# 1. Get the target company
bin/ch profile 12345678

# 2. Get all officers
bin/ch officers 12345678

# 3. Get PSCs
bin/ch pscs 12345678

# 4. For each officer, extract their officer_id from links.officer.appointments
#    then get their other appointments
bin/ch appointments <officer_id>

# 5. For interesting connected companies, repeat steps 1-4
```

### Check for red flags

```bash
# Filing patterns
bin/ch filings 12345678 accounts

# Charges (secured lending)
bin/ch charges 12345678

# Insolvency
bin/ch insolvency 12345678
```

## Error Handling

- **404**: Entity not found (dissolved companies may still be accessible)
- **429**: Rate limited — wait and retry
- **Other errors**: Check the error JSON for details

## Notes

- Company numbers are 8 characters, zero-padded (e.g., "00445790" not "445790")
- Scottish companies start with "SC", Northern Irish with "NI"
- The API returns dates as "YYYY-MM-DD" strings
- Officer appointment links contain the officer_id needed for cross-referencing
