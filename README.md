<div align="center">
  <img src="RayStudio.png" alt="RayStudio Logo" width="120"/>

  <h1>RepoLedger</h1>
</div>

[![CodeQL](https://github.com/9t29zhmwdh-coder/RepoLedger/actions/workflows/github-code-scanning/codeql/badge.svg)](https://github.com/9t29zhmwdh-coder/RepoLedger/security/code-scanning) [![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/9t29zhmwdh-coder/RepoLedger/badge)](https://securityscorecards.dev/viewer/?uri=github.com/9t29zhmwdh-coder/RepoLedger)
[![Pages](https://img.shields.io/badge/Live-RepoLedger-a5762e)](https://raystudio.ch/RepoLedger/) ![No backend](https://img.shields.io/badge/Backend-none-2f7d5c) ![AI | Claude Code](https://img.shields.io/badge/AI-Claude_Code-black?logo=anthropic&logoColor=white)

[🇩🇪 Deutsche Version](README.de.md)

A free, client-side GitHub portfolio dashboard. Enter any public GitHub username to see CI status, open PRs, security alerts and licensing at a glance, with a link straight to each repo.

> **How it runs:** RepoLedger is a single static HTML page with no backend and no build step. Your browser calls the public GitHub API directly; nothing is proxied, logged, or stored anywhere, including by us.

## Try it

**[raystudio.ch/RepoLedger](https://raystudio.ch/RepoLedger/)**

Type in any GitHub username and press "Load dashboard". No sign-up, no installation.

## What it shows

- **CI & Security**: latest CI run status, open PRs, open Dependabot + code scanning alerts
- **Activity**: last push date, primary language, star count
- **Licensing**: detects a MIT/Community + `LICENSE.COMMERCIAL` dual-licensing setup per repo

Each section can be toggled on or off independently, and the page works in English, German or French.

## Rate limits

Without a token, GitHub allows 60 unauthenticated API calls per hour per IP address, shared across everyone on your network. That's enough for a handful of repos but tight for a large account. Add your own [personal access token](https://github.com/settings/tokens) (no scopes needed for public data) in the optional field to raise this to 5,000 calls/hour. The token is only ever sent directly from your browser to `api.github.com`, never anywhere else.

## Run your own copy

This is a single self-contained `index.html`, no build step, no dependencies. Fork this repo, enable GitHub Pages on the fork (Settings → Pages → Deploy from branch → `main`), and you have your own copy at `https://<you>.github.io/RepoLedger/`. Or just download `index.html` and open it locally.

## License

MIT, see [LICENSE](LICENSE).

---

**Author:** [Rafael Yilmaz](https://github.com/9t29zhmwdh-coder) · **Status:** Active · **License:** MIT
