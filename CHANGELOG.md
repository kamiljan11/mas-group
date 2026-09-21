# Changelog

Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), wersjonowanie: [SemVer](https://semver.org/).
Kazdy PR dopisuje zmiany do [Unreleased]; przy release przenosimy pod numer wersji z data.

## [Unreleased]
### Added
- Pipeline jakosci: CI (build/lint/typecheck/test/semgrep/audit/licencje), Claude review na PR, szablony dokumentacji
- `docs/ARCHITECTURE.md`, `docs/adr/0001-public-repo-is-a-reference-not-the-source.md`, `LICENSE`, `docs/GLOSSARY.md`, `.github/pull_request_template.md`

### Changed
- Wszystkie dokumenty (README, RUNBOOK, ARCHITECTURE, GLOSSARY, CLAUDE.md, ADR 0001 z adnotacją) wskazują platformę `https://maskalkulator.lovable.app`; `www.masgroup.is` to strona firmy, nie aplikacja
- README/RUNBOOK: link "Live" poprawiony na `https://www.masgroup.is` — golo `masgroup.is` (bez www) nie ma nasluchu HTTPS (curl -v: connection timeout), tylko `http://` robi redirect na `www`
- `docs/RUNBOOK.md` wypelniony realnymi danymi (healthcheck, kontakty) zamiast szablonowych `[...]`

### Fixed
- `e2e/smoke.spec.ts` usuniety — byl martwy (wymagal `@playwright/test`, ktorego repo bez `package.json` nie ma; nigdy nie mogl sie uruchomic)
