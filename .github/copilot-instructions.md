# Copilot Instructions for RepoLedger
RepoLedger is a free, client-side GitHub portfolio dashboard. It shows CI status, open PRs, security alerts, and licensing for any public GitHub username, with no backend and no build step.
## Code style
- Functions stay small and single-purpose, prefer under 20 lines
- Naming: verb+noun for functions, clear intent for variables, no x/temp/data
- Constants in UPPER_SNAKE_CASE
- Comments explain WHY, never WHAT
- No speculative abstractions
## Text and documentation
- Never use em-dash, en-dash, or a spaced hyphen as a sentence-break substitute, anywhere. Rephrase instead
- README.md and README.de.md must stay in sync (this repo's structure recently changed, use the CURRENT sections in both files as the sync baseline, do not reintroduce old removed sections)
- Any functional change needs a CHANGELOG.md entry and follows semantic versioning
- No separate License badge in README (intentional convention)
## Git workflow
- Branch protection on main: no direct pushes, no force pushes, PR required
- Semantic commit messages: type(scope): description
- One commit = one logical change
## Security
- Never commit secrets/API keys/tokens
- Validate input at actual boundaries only
- Flag security regressions instead of working around them
## Before opening a PR
- Run tests/build, no PR with failing checks
- Keep diff scoped to the task
