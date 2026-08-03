# Contributing

## For YouGov Scraper

This repo is a **derived scraper** — it scrapes YouGov job listings for Romania and publishes them to peviitor.ro.

### Development

```bash
npm install              # install dependencies
npm run test:unit        # run unit tests
npm run test:integration # run integration tests (needs ANAF)
npm run test:e2e         # run e2e tests (needs real network)
```

### Key Files

| File | Description |
|---|---|
| `scraper/config/company.json` | Company identity (single source of truth) |
| `scraper/config/scraper.json` | API endpoints (Workday base + path) |
| `scraper/index.js` | Main scraper logic |
| `scraper/api.js` | Peviitor API client (job + company cores) |
| `tests/` | Unit/integration/e2e tests |

### Updating for New Companies

To derive a new scraper from this repo:

1. Fork this repo or use `--template` flag
2. Update `scraper/config/company.json` with new company identity
3. Rewrite scraper logic in `scraper/index.js` for new data source
4. Update all test files (search for remaining YouGov references)
5. Update docs, workflows, and README
6. Verify CI passes

### CI

- `job-seeker-ro-spider.yml` — runs the scraper on schedule (daily 06:00)
- `automation-testing.yml` — runs validation tests on schedule
- `job-deep-validate.yml` — manual deep validation (browser mode)
- `automation-template-sync-check.yml` — weekly template sync check
