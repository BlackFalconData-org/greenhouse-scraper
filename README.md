# Greenhouse Scraper

Scrape job listings from Greenhouse-powered career sites. Free public API, no proxy needed. Salary data, departments, questions, metadata.

**[Run on Apify →](https://apify.com/blackfalcondata/greenhouse-scraper)**

---

## Key features

🔍 **Smart search with filters**

Search by keyword, location, and multiple filters. Smart input resolution ensures you always get results.

📄 **Detail enrichment**

Fetch full job descriptions, salary data, employer profiles, and contact information for each listing.

🔄 **Incremental mode**

Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

⚡ **Compact output for AI agents**

Core-fields-only mode optimized for MCP and AI agent workflows. Description truncation to control output size.

---

## Use cases

**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from the source on a schedule. Export to CSV, JSON, or directly to your database.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from the source.

**AI and LLM workflows**
Use compact mode and description truncation to feed data into AI agents, MCP servers, and LLM pipelines without exceeding token budgets.

---

## Quick start

```json
{
  "maxResults": 50,
  "includeDetails": true
}
```

---

## Input parameters

| Parameter | Type | Default | Description |
|-----------|------|---------|-------------|
| `boardTokens` | array | — | Greenhouse board tokens or URLs. Example: 'airbnb' or 'https://boards.greenhouse.io/airbnb'. |
| `query` | string | — | Filter jobs by keyword (matched against title and description). |
| `location` | string | — | Filter by location (substring match, e.g. 'London' or 'Remote'). |
| `department` | string | — | Filter by department name (substring match, e.g. 'Engineering'). |
| `maxResults` | integer | `0` | Maximum total results across all boards (0 = unlimited). |
| `includeDetails` | boolean | `false` | Fetch pay transparency + application questions per job (slower — one extra API call per job). |
| `descriptionMaxLength` | integer | `0` | Truncate HTML description to N characters. 0 = no truncation. |
| `compact` | boolean | `false` | Return only core fields (for AI-agent/MCP workflows). |
| `incrementalMode` | boolean | `false` | Only return new or changed jobs since last run. |
| `stateKey` | string | — | Custom key for incremental state (default: auto-generated from board tokens). |

---

## FAQ

<!-- WRITE: 4-6 Q&A pairs relevant to this product -->

**How does incremental mode work?**
Each listing gets a content hash. On subsequent runs, only new or changed listings are emitted — saving time, compute, and storage.

---

## Known limitations

<!-- WRITE: 4-6 honest limitations -->

- <!-- WRITE: limitation 1 -->
- <!-- WRITE: limitation 2 -->

---

## Related products by Black Falcon Data

| Product | Description |
|:--------|:------------|
| [StepStone Jobs API](https://github.com/BlackFalconData-org/stepstone-jobs-api) | Job listings from 18 European portals |
| [Company Jobs Tracker](https://github.com/BlackFalconData-org/company-jobs-tracker-api) | Track new/removed jobs per company |
| [Indeed Jobs Feed](https://github.com/BlackFalconData-org/indeed-jobs-feed) | Indeed job listings with salary data |
| [Glassdoor Jobs Feed](https://github.com/BlackFalconData-org/glassdoor-jobs-feed) | Glassdoor listings with company ratings |
| [Arbeitsagentur Jobs Feed](https://github.com/BlackFalconData-org/arbeitsagentur-jobs-feed) | Germany's federal job portal (1M+ listings) |
| [Naukri Jobs Feed](https://github.com/BlackFalconData-org/naukri-jobs-feed) | India's largest job portal |
| [Bilbasen Scraper](https://github.com/BlackFalconData-org/bilbasen-scraper) | Denmark's largest car marketplace |

---

*Last updated: 2026 03*
