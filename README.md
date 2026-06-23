# Greenhouse Scraper

Scrape job listings from Greenhouse-powered career sites. Free public API, no proxy needed. Salary data, departments, questions, metadata.

**[Greenhouse Scraper 💰 $0.95/1K on Apify →](https://apify.com/blackfalcondata/greenhouse-scraper?fpr=1h3gvi)**


## 🚀 How to use this actor

> ### 💚 $5 free Apify credits — every month
> No credit card required. No commitment. Cancel anytime.

### 👉 [Sign up free on Apify →](https://console.apify.com/sign-up?fpr=1h3gvi)

1. **Click sign up** — pick GitHub, Google, or email; takes ~30 seconds
2. **Open this actor** — input is pre-filled with a working example
3. **Click Start** — export results as JSON, CSV, or Excel

Your **$5 monthly platform credit** is enough to run this actor right away — and again every month — scraping typically several hundred to several thousand results per run, depending on your input.



## 🚀 How to use this actor

> ### 💚 $5 free Apify credits — every month
> No credit card required. No commitment. Cancel anytime.

### 👉 [Sign up free on Apify →](https://console.apify.com/sign-up?fpr=1h3gvi)

1. **Click sign up** — pick GitHub, Google, or email; takes ~30 seconds
2. **Open this actor** — input is pre-filled with a working example
3. **Click Start** — export results as JSON, CSV, or Excel

Your **$5 monthly platform credit** is enough to run this actor right away — and again every month — scraping typically several hundred to several thousand results per run, depending on your input.


---

## Key features








**Search with filters** — Search by keyword and location. Filter by description format, and more.

**Detail enrichment** — Fetch full job descriptions, salary data, contact information for each listing.

**Incremental mode** — Only get new or changed listings since your last run. Content hash per listing — no duplicates, no re-processing.

**Change classification** — Track cross-run repost detection across runs. Build audit trails of how listings evolve over time.

**Compact output** — Emit core fields only (AI-agent / MCP-friendly). Keeps response size small for LLM workflows.

**Description truncation** — Cap description length per listing to control output size and cost.

**Result cap** — Stop after N listings (up to 10.000). Set to 0 for the full catalog.

**Export anywhere** — Download as JSON, CSV, or Excel. Stream via Apify API, webhooks, or integrations with Make, Zapier, Airbyte, Keboola.

**Structured data** — Every listing returns the same schema with consistent field naming. All fields always present — `null` when unavailable, never omitted.

---

## Use cases








**Data pipeline automation**
Integrate with your ETL pipeline to collect structured listings from 0.95 on a schedule. Export to CSV, JSON, or directly to your database. Use compact mode to control output size.

**Market research**
Monitor listings, track trends, and analyze market dynamics with structured, deduplicated data from 0.95.

**Change monitoring**
Run daily or hourly in incremental mode to capture only new, updated, or expired listings. Perfect for price-tracking, churn analysis, and alerting pipelines.

**Compensation benchmarking**
Aggregate salary ranges across roles, industries, and locations on 0.95 to inform pricing decisions, hiring plans, or candidate negotiations.

**Lead generation**
Extract employer contact details alongside listings to build outreach lists for recruiters, staffing agencies, or B2B sales teams.

**AI / LLM training data**
Structured JSON per listing is ready for RAG pipelines, embeddings, and agent workflows. Compact mode trims tokens for LLM context windows.

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


## Output fields

Every listing returns the same 26-field schema. Missing values are `null` — never omitted.

- `jobId`
- `greenhouseId`
- `internalJobId`
- `title`
- `company`
- `location`
- `department`
- `offices`
- `description`
- `employmentType`
- `workplaceType`
- `url`
- `applyUrl`
- `requisitionId`
- `language`
- `salaryMin`
- `salaryMax`
- `salaryCurrency`
- `salaryPeriod`
- `questions`
- `metadata`
- `postedDate`
- `updatedAt`
- `scrapedAt`
- `portalUrl`
- `source`


## Sample output

One object per listing. Here is a real example from a production run:

```json
{
  "jobId": "gh-7649441",
  "greenhouseId": 7649441,
  "internalJobId": 3369660,
  "title": "Account Executive (12 Month FTC)",
  "company": "Airbnb",
  "location": "Paris, France",
  "department": "Sales",
  "offices": [
    "Paris, France"
  ],
  "description": "&lt;div class=&quot;content-intro&quot;&gt;&lt;p&gt;&lt;span style=&quot;font-family: helvetica, arial, sans-serif; font-size: 12pt;&quot;&gt;Airbnb was born in 2007 when two hosts…",
  "employmentType": null,
  "workplaceType": "Hybrid",
  "url": "https://careers.airbnb.com/positions/7649441?gh_jid=7649441"
}
```

*Truncated — full records contain 26 fields. See Output fields for the complete schema.*


**[Try Greenhouse Scraper - Career Site Jobs now — $5 free credit, no credit card →](https://apify.com/blackfalcondata/greenhouse-scraper?fpr=1h3gvi)**


## Pricing

Pay only for what you extract. No subscription required — Apify's free $5 credit covers thousands of results.

| Event | Price (USD) |
| --- | --- |
| Actor Start | $0.005 |
| Result | $0.002 |

See the [actor on Apify](https://apify.com/blackfalcondata/greenhouse-scraper?fpr=1h3gvi) for current pricing.

---

## Related products by Black Falcon Data








- [StepStone Scraper](https://apify.com/blackfalcondata/stepstone-scraper?fpr=1h3gvi) — Job listings from 18 European portals
- [Indeed Job Scraper](https://apify.com/blackfalcondata/indeed-job-scraper?fpr=1h3gvi) — Indeed job listings with salary data
- [LinkedIn Jobs Scraper](https://apify.com/blackfalcondata/linkedin-jobs-scraper?fpr=1h3gvi) — World's largest professional network — global job listings, no login required
- [Glassdoor Job Scraper](https://apify.com/blackfalcondata/glassdoor-job-scraper?fpr=1h3gvi) — Glassdoor listings with company ratings
- [Arbeitsagentur Scraper](https://apify.com/blackfalcondata/arbeitsagentur-scraper?fpr=1h3gvi) — Germany's official job portal (1M+ listings)
- [SEEK Scraper](https://apify.com/blackfalcondata/seek-scraper?fpr=1h3gvi) — Australia & NZ's largest job board

---


## About Black Falcon Data

Black Falcon Data builds production-grade web scrapers for job boards and marketplace data. Browse our full actor catalog at [www.blackfalcondata.com](https://www.blackfalcondata.com).

---

## Getting started with Apify

New to Apify? [Create a free account with $5 credit](https://console.apify.com/sign-up?fpr=1h3gvi) — no credit card required.

1. [Sign up free](https://console.apify.com/sign-up?fpr=1h3gvi) — $5 credit included
2. Open the actor and paste your input
3. Click Start — results download as JSON, CSV, or Excel

Need more volume? [See pricing](https://apify.com/pricing?fpr=1h3gvi).

---

---

*Last updated: 2026 03*
