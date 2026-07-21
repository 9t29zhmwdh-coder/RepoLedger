<div align="center">
  <img src="RayStudio.png" alt="RayStudio Logo" width="120"/>

  <h1>RepoLedger</h1>
</div>

[![CodeQL](https://github.com/9t29zhmwdh-coder/RepoLedger/actions/workflows/github-code-scanning/codeql/badge.svg)](https://github.com/9t29zhmwdh-coder/RepoLedger/security/code-scanning) [![OpenSSF Scorecard](https://api.securityscorecards.dev/projects/github.com/9t29zhmwdh-coder/RepoLedger/badge)](https://securityscorecards.dev/viewer/?uri=github.com/9t29zhmwdh-coder/RepoLedger) [![OpenSSF Best Practices](https://www.bestpractices.dev/projects/13686/badge)](https://www.bestpractices.dev/projects/13686)

[![Pages](https://img.shields.io/badge/Live-RepoLedger-a5762e)](https://raystudio.ch/RepoLedger/) ![No backend](https://img.shields.io/badge/Backend-none-2f7d5c) ![AI | Claude Code](https://img.shields.io/badge/AI-Claude_Code-black?logo=anthropic&logoColor=white)

[🇬🇧 English Version](README.md)

Ein kostenloses, rein clientseitiges GitHub-Portfolio-Dashboard. Gib einen beliebigen öffentlichen GitHub-Benutzernamen ein und sieh CI-Status, offene PRs, Security-Meldungen und Lizenzierung auf einen Blick, inklusive Link zum jeweiligen Repo.

> **So läuft es:** RepoLedger ist eine einzige statische HTML-Seite, kein Backend, kein Build-Schritt. Dein Browser ruft die öffentliche GitHub-API direkt auf, nichts wird irgendwo geloggt oder gespeichert, auch nicht von uns.

## Ausprobieren

**[raystudio.ch/RepoLedger](https://raystudio.ch/RepoLedger/)**

Einfach einen GitHub-Benutzernamen eingeben und "Load dashboard" klicken. Keine Anmeldung, keine Installation.

## Was angezeigt wird

- **CI & Security**: letzter CI-Lauf-Status, offene PRs, offene Dependabot- und Code-Scanning-Meldungen
- **Aktivität**: letzter Push, Hauptsprache, Star-Anzahl
- **Lizenzierung**: erkennt pro Repo eine MIT/Community + `LICENSE.COMMERCIAL`-Dual-Licensing-Struktur

Jeder Bereich lässt sich einzeln ein-/ausblenden, die Seite läuft auf Englisch, Deutsch oder Französisch.

## Rate-Limits

Ohne Token erlaubt GitHub 60 unauthentifizierte API-Aufrufe pro Stunde und IP-Adresse, geteilt mit allen im selben Netzwerk. Das reicht für ein paar Repos, wird aber bei einem grossen Konto knapp. Mit einem eigenen [Personal Access Token](https://github.com/settings/tokens) (keine Scopes nötig für öffentliche Daten) im optionalen Feld steigt das auf 5'000 Aufrufe/Stunde. Der Token geht ausschliesslich direkt von deinem Browser an `api.github.com`, nirgendwo sonst hin.

## Eigene Kopie betreiben

Das Ganze ist eine einzige, in sich geschlossene `index.html`, kein Build-Schritt, keine Abhängigkeiten. Dieses Repo forken, auf dem Fork GitHub Pages aktivieren (Settings → Pages → Deploy from branch → `main`), fertig ist die eigene Kopie unter `https://<du>.github.io/RepoLedger/`. Oder einfach `index.html` herunterladen und lokal öffnen.

## Lizenz

MIT, siehe [LICENSE](LICENSE).

---

**Autor:** [Rafael Yilmaz](https://github.com/9t29zhmwdh-coder) · **Status:** Active · **Lizenz:** MIT
