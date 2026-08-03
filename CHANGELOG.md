# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.1] - 2026-08-03

### Changed
- Migrated repo to EPAM template structure: scraper code moved to `scraper/` (index, company, anaf, api, job-validator, markdown-generator, demoanaf, validate-jobs), company identity in `scraper/config/company.json`, API config in `scraper/config/scraper.json`
- All Solr operations now go through the Peviitor API via `scraper/api.js` — no direct SOLR access, no `SOLR_AUTH` needed
- Root docs moved to `ai/` (AGENTS, INSTRUCTIONS, files, company-model, job-model, etc.)
- New workflows: `job-deep-validate.yml` (manual Playwright deep validation), `automation-template-sync-check.yml` (weekly template sync check)
- `tests/validate-yougov-jobs.js`: multi-mode validator (`--head`, `--content`, `--browser`, `--timeout`)
- Workflows upsert `scraperFile` via the Peviitor API company core
- `docs/index.html`: read company fields from `cfg.company`/`cfg.id`

## 1.0.0 - 2026-04-16

### Added
- Initial release as derived scraper from EPAM template
- Company: YOUGOV CP ROMANIA S.R.L. (CIF: 48869513)
- Data source: Workday JSON API
- Public peviitor.ro integration
