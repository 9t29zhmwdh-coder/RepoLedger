# Security Policy: RepoLedger

## Supported Versions

| Version | Supported |
|---------|-----------|
| 1.1.x   | ✅        |
| < 1.1   | ❌        |

## Reporting a Vulnerability

**Do not open a public GitHub issue for security vulnerabilities.**

Report via [GitHub Security Advisory](https://github.com/9t29zhmwdh-coder/RepoLedger/security/advisories/new)
or contact the maintainer directly via the GitHub profile.

Include: description, steps to reproduce, potential impact, suggested fix.
Response within 7 days.

## Security Design

RepoLedger is a single static HTML page. There is no backend, no build step and
no server of mine anywhere in the path.

- Your browser calls `api.github.com` directly. Nothing is proxied through, logged by, or stored on any infrastructure of mine, because none exists
- The username you type is sent to GitHub as part of the API path and nowhere else. It is URL-encoded before being placed in the path
- An optional personal access token, if you supply one to raise the rate limit, stays in the page for the duration of the session. It is not persisted and not transmitted anywhere except to GitHub in the `Authorization` header
- The page reads public GitHub data only. It performs no write operations, so a token with no scopes is sufficient
- Values coming back from the API are HTML-escaped before being rendered

## About the escaping

The table renders data belonging to whichever account you point the page at,
which may not be yours. GitHub constrains the fields currently displayed:
repository names allow only `A-Za-z0-9._-`, languages and SPDX identifiers come
from fixed lists, and the rest are numbers and dates. None of them can carry
markup today.

The values are escaped anyway. The constraint that makes them safe is GitHub's,
not this page's, and it holds only for exactly these fields. A later change
adding a repository description or a topic list, both of which are free text,
would otherwise introduce an injection point with nothing in the code to catch
it.

**Last updated: 2026-07-31**
