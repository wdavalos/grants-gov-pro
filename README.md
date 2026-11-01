# Grants.gov Pro

Enterprise-grade Grants.gov scraper and search actor for federal grant opportunities. Queries the official Grants.gov search API to produce structured, keyword-searchable rows of federal funding opportunities — no scraping, no API key, no login.

**Store page:** https://apify.com/red.cars/grants-gov-pro
**ScraperFleet:** https://scraperfleet.com/actors/grants-gov-pro/

## What it does

- Keyword and agency queries across 100+ federal agencies (NSF, NIH, HHS, ED, USDA, EPA, DOD, and more)
- Full filter coverage: opportunity status (forecasted/posted/closed/archived), document type (synopsis/forecast/full announcement), eligibility codes (20+), funding category, funding instrument (grant/cooperative agreement/other/procurement contract), CFDA / Assistance Listing
- Deadline-window filter (`closeWithinDays`): keep only opportunities closing within the next N days (US Eastern time), so a grant writer can pull "everything closing this month" in one run
- Sort by open date, close date, or relevance; fetch single opportunities by their number
- Up to 1,000 rows per query, live from Grants.gov's official API

## Output fields

| Field | Description |
| --- | --- |
| id | Grants.gov opportunity id |
| opportunityNumber | Opportunity number, e.g. 21-595 |
| title | Opportunity title |
| agency | Full agency name |
| agencyCode | Agency code, e.g. NSF |
| status | posted / forecasted / closed / archived |
| docType | synopsis / forecast / full announcement |
| openDate | Opening date (MM/DD/YYYY) |
| closeDate | Closing date (MM/DD/YYYY) |
| cfdaList | Assistance Listing numbers |
| url | Direct link to the opportunity on grants.gov |

## Comparison

| | Grants.gov Pro | us-grants-funding-tracker | us-federal-grant-scraper |
| --- | --- | --- | --- |
| Source | Grants.gov API (official) | grants.gov scraping | grants.gov scraping |
| API key needed | No | No | No |
| Status filter | forecasted / posted / closed / archived | posted only | posted only |
| Eligibility filter | Yes (20+ codes) | No | Limited |
| Funding category filter | Yes | No | Limited |
| Funding instrument filter | Yes (grant / CA / other / PC) | No | No |
| CFDA / Assistance Listing filter | Yes | No | No |
| Deadline window filter (closing within N days) | Yes | No | No |
| Sort by open date / close date / relevance | Yes | No | No |
| Price | $0.005/run + $2.00 per 1,000 rows | ~$2+ per 1,000 rows | ~$2+ per 1,000 rows |

The category leader on the Apify Store has about 60 users total and none of the competing scrapers expose Grants.gov's full filter set. This actor does, plus the deadline-window filter grant writers actually ask for.

## Use cases

- Grant writers and nonprofit development teams: find open federal opportunities that match your mission and filter to deadlines closing within the next 30 days.
- Proposal consultants: monitor a portfolio of agencies, categories or Assistance Listings and track open vs. closed vs. forecasted opportunities.
- Researchers and universities: shortlist fundable opportunities and analyze what agencies actually funded via closed/archived history.

## Pricing

$0.005 per actor run + $2.00 per 1,000 result rows on Apify's pay-per-event model. The zero-result hint row is the only row billed when nothing matches.

## FAQ

**Do I need a Grants.gov account or API key?**
No. The actor uses Grants.gov's public search API. No key, no registration, no login.

**How current is the data?**
Rows come live from Grants.gov at run time, the same source the Grants.gov search page uses.

**How many results can I get?**
Up to 1,000 rows per run. Grants.gov's API serves deep pages in steps; widen your filters rather than paging past 1,000.

**What does the deadline window filter do?**
`closeWithinDays` keeps only opportunities whose close date falls within the next N days (in US Eastern time), so a grant writer can pull "everything closing this month" in one run.

**Why do closed/archived opportunities matter?**
Historical awards show what agencies actually funded, useful for pipeline research and competitor analysis.

**What if my search returns nothing?**
You get a single hint row explaining which filter to loosen, and nothing else is billed.

## Pair it with

- [Academic Research MCP](https://apify.com/red.cars/academic-research-mcp) for the research side: the grants give the funding landscape, the MCP runs the literature and citation search.
