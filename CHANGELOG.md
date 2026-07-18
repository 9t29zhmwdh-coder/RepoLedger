<div align="center">
  <img src="RayStudio.png" alt="RayStudio Logo" width="120"/>

  <h1>Changelog</h1>
</div>

[🇩🇪 Deutsche Version](CHANGELOG.de.md)

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [1.0.0] - 2026-07-13

### Added

- Initial release: single-file, client-side GitHub portfolio dashboard.
- CI status, open PRs, and Dependabot/code scanning alert counts per repo.
- Activity view: last push date, primary language, star count.
- Licensing view: detects a MIT + `LICENSE.COMMERCIAL` dual-licensing setup per repo.
- Optional personal access token field to raise the unauthenticated 60 req/hour limit to 5,000 req/hour.
- English, German and French UI, switchable at runtime.
- Concurrency-limited fetching to stay well under GitHub's secondary rate limits even for large accounts.
