# ADR-0001 — Ten publiczny repo to referencja, nie źródło aplikacji

Data: 2026-09-05 | Status: przyjęte (widoczne w historii repo od 2026-08-10)

**Kontekst:** `mas-group` jest publiczne na GitHubie (portfolio/audyt), ale sam produkt
(platforma B2B na `masgroup.is`) ma logikę cenową, marże, dane klientów i strukturę prowizji,
których Kamil nie chce trzymać w publicznym repo. Do 2026-08-10 README twierdziło wprost
"The application source is private" — sformułowanie ogólnikowe, które nie mówiło, GDZIE kod
faktycznie jest, tylko że nie tutaj.

**Decyzja:** `mas-group` zawiera wyłącznie dokumentację (README, ARCHITECTURE, ADR, RUNBOOK,
GLOSSARY) — zero `package.json`, zero `src/`. Rzeczywisty kod platformy żyje w osobnym repo
`maskalkulator` i jest nazwany wprost w sekcji "Source" README (commit
`docs: sprostowanie sekcji Source`, 2026-08-10), zamiast ukryty za ogólnym "private".

**Rozważone alternatywy:**
- *Trzymać ogólne "Source is private" bez nazwy repo* — odrzucone 2026-08-10: nie mówi nic
  weryfikowalnego i brzmi jak wymówka zamiast jak fakt.
- *Umieścić kod aplikacji w tym samym publicznym repo* — odrzucone: platforma ma ceny, marże i
  dane operacyjne klientów MAS Group, których Kamil nie chce publicznie widocznych.
- *Prywatne monorepo bez żadnej publicznej wizytówki* — odrzucone: portfolio/audyt potrzebuje
  czegoś konkretnego do pokazania bez proszenia o dostęp za każdym razem.

**Konsekwencje:**
- CI w tym repo (`quality.yml`) sprawdza tylko treść dokumentacji (gitleaks, Semgrep) — kroki
  npm (lint/typecheck/test/build) pomijają się przez `hashFiles('package.json')`, bo nie ma czego
  budować. Zielona bramka oznacza "brak sekretów w docs", nie "platforma działa".
- Jedyny wiarygodny "smoke test" tego repo to zewnętrzny `curl -I https://www.masgroup.is`
  (patrz `docs/RUNBOOK.md`) — nie lokalny test frameworka.
- **Nierozwiązane świadomie**: widoczność `maskalkulator` na GitHubie (publiczne/prywatne) to
  osobna, jeszcze nie podjęta decyzja Kamila — ten ADR dotyczy WYŁĄCZNIE podziału
  wizytówka/źródło, nie tego, kto może czytać kod w `maskalkulator`. Nie zmieniaj widoczności
  tamtego repo przy okazji tego zadania.

**Pułapki dla przyszłego siebie:**
- Nie dopisuj tu kodu "tymczasowo, żeby coś pokazać" — jeśli platforma kiedyś ma być publiczna,
  to osobna, świadoma decyzja (i osobny ADR), nie commit poboczny.
- Link "Live" w README ma iść na `www.masgroup.is`, nie na gołe `masgroup.is` — apeks nie ma
  nasłuchu HTTPS (zweryfikowane `curl -v`, connection timeout); patrz `docs/ARCHITECTURE.md`.
