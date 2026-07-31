<div align="center">
  <img src="RayStudio.png" alt="RayStudio Logo" width="120"/>

  <h1>Changelog</h1>
</div>

[🇩🇪 Deutsche Version](CHANGELOG.de.md)

All notable changes to this project will be documented in this file.
Format based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [1.1.6] - 2026-07-31

### Changed

- Both READMEs now open with what GitHub does not give you, which is any view of your repositories together, so finding the one with the red build means opening tabs until you hit it. A short paragraph says the page only reads: issues, merges and dismissals still happen on GitHub.
- The privacy note said nothing is stored "including by us". There is no "us"; it now reads "by me", matching the first-person convention the other documents follow.

---

## [1.1.5] - 2026-07-29

### Security

- The release workflow no longer grants `contents: write` for its whole run. The permission moves to the one job that publishes the release, and everything else runs with `contents: read`. OpenSSF Scorecard scores the Token-Permissions check 0 out of 10 whenever any workflow holds a top-level write permission, regardless of how little of the run needs it, so this single line was what held the check at zero.

---

## [1.1.4] - 2026-07-29

### Added

- `.github/workflows/release.yml`. Pushing a version tag produced nothing here: the tag landed in the repository and no release was ever created, which is how several versions ended up tagged but unreleased. The gap only showed when the tag list was compared against the release list. Release notes are taken from the matching `CHANGELOG.md` section, so they are not maintained separately from the file.

---

## [1.1.3] - 2026-07-29

### Changed

Dependency and workflow updates merged since 1.1.2:

- chore(ci): bump the actions group across 1 directory with 3 updates

---

## [1.1.2] - 2026-07-28

### Changed

- CodeQL moved from GitHub's default setup to an advanced setup with a committed `.github/workflows/codeql.yml`. The default setup skips pull requests that touch no code of a given language, so a dependency pull request changing only a lock file reported `skipping` on the required `Analyze (...)` checks forever and could never be merged. The workflow runs on every pull request regardless of what changed and uses the `security-extended` query suite, which the default setup does not allow choosing. Required checks are unchanged.
- The CodeQL job requests only `security-events: write` beyond the workflow-level `contents: read`. Repeating read grants at job level is what OpenSSF Scorecard counts as excessive token permissions, and it costs the full `Token-Permissions` score.

## [1.1.1] - 2026-07-28

### Added

- `.github/dependabot.yml`, with grouped weekly updates. The file was missing, and without it there are no version updates at all: repository security alerts only fire for disclosed vulnerabilities, which is how action pins across this portfolio quietly went stale. Follows `engineering-standards` v0.10.0.

### Fixed

- `actions/checkout` pins now carry the full version in the comment instead of a bare major, and all workflows use the same SHA.

## [1.1.0] - 2026-07-25

### Fixed

- CI and Security columns silently fell back to "no CI" / "needs token" whenever the underlying GitHub API call failed for any reason, including hitting the unauthenticated rate limit partway through a larger account. A rate-limited repo is now shown distinctly ("rate limited") instead of looking identical to a repo that genuinely has no CI or a genuinely missing token, and a status banner explains what happened when it occurs.

## [1.0.1] - 2026-07-20

### Changed

- OpenSSF Scorecard workflow and badge.
- `copilot-instructions.md` for consistent AI-assisted contributions.
- Added a CodeQL badge and fixed README badge-row isolation.
- Split the README's security/CI badges onto their own line, separate from the platform/tech/AI badges (they were rendering as a single merged line).

## [1.0.0] - 2026-07-13

### Added

- Initial release: single-file, client-side GitHub portfolio dashboard.
- CI status, open PRs, and Dependabot/code scanning alert counts per repo.
- Activity view: last push date, primary language, star count.
- Licensing view: detects a MIT + `LICENSE.COMMERCIAL` dual-licensing setup per repo.
- Optional personal access token field to raise the unauthenticated 60 req/hour limit to 5,000 req/hour.
- English, German and French UI, switchable at runtime.
- Concurrency-limited fetching to stay well under GitHub's secondary rate limits even for large accounts.
