<div align="center">
  <img src="RayStudio.png" alt="RayStudio Logo" width="120"/>

  <h1>Changelog</h1>
</div>

[🇬🇧 English Version](CHANGELOG.md)

Alle relevanten Änderungen an diesem Projekt werden hier dokumentiert.
Format nach [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

---

## [Unreleased]

### Fixed

- CI- und Security-Spalte fielen stillschweigend auf "kein CI"/"Token nötig" zurück, sobald der zugrunde liegende GitHub-API-Call aus irgendeinem Grund fehlschlug, auch wenn mitten im Durchlauf das unauthentifizierte Rate-Limit erreicht wurde. Ein rate-limitiertes Repo wird jetzt klar als "Rate-Limit" angezeigt statt identisch mit einem Repo ohne CI oder ohne Token auszusehen, dazu ein Status-Hinweis, wenn das passiert.

## [1.0.1] - 2026-07-20

### Geändert

- OpenSSF Scorecard Workflow und Badge.
- `copilot-instructions.md` für konsistente KI-unterstützte Beiträge.
- CodeQL-Badge ergänzt, Badge-Zeilen-Isolation im README korrigiert.
- Sicherheits-/CI-Badges und Tech-/AI-Badges in getrennte README-Zeilen aufgeteilt (rendeten vorher als eine Zeile).

## [1.0.0] - 2026-07-13

### Added

- Erstes Release: rein clientseitiges GitHub-Portfolio-Dashboard, eine einzige Datei.
- CI-Status, offene PRs und Dependabot-/Code-Scanning-Meldungen pro Repo.
- Aktivitäts-Ansicht: letzter Push, Hauptsprache, Star-Anzahl.
- Lizenzierungs-Ansicht: erkennt pro Repo eine MIT + `LICENSE.COMMERCIAL`-Dual-Licensing-Struktur.
- Optionales Personal-Access-Token-Feld, hebt das unauthentifizierte Limit von 60 auf 5'000 Aufrufe/Stunde an.
- Englische, deutsche und französische Oberfläche, zur Laufzeit umschaltbar.
- Nebenläufigkeits-begrenztes Abrufen, um auch bei grossen Konten deutlich unter GitHubs Sekundär-Rate-Limits zu bleiben.
