# Quality backlog — mas-group

Świadomie odłożone przy PG v3 github-ready (2026-09-05). Nie blokuje merge'a tego PR.

| # | Co | Dlaczego odłożone | Ryzyko jak zostanie |
|---|---|---|---|
| 1 | `eslint.config.mjs` (strict baseline) dodany przez bootstrap, ale nie ma żadnego pliku JS/TS do lintowania | Repo nie ma kodu — placeholder na wypadek, gdyby kiedyś tu wylądował kod | Zerowe — plik jest bierny |
| 2 | Widoczność repo `maskalkulator` (publiczne/prywatne) niejasna w README ("access may be restricted") | Osobna decyzja Kamila, poza zakresem tego zadania (patrz `docs/adr/0001-...md`) | Niskie — stan opisany uczciwie, nie zgadywano i nie zmieniano widoczności |
| 3 | `https://masgroup.is` (bez `www`) nie ma nasłuchu HTTPS — problem hostingu strony firmy (nie platformy, ta stoi na `maskalkulator.lovable.app`), nie tego repo | Naprawa wymaga panelu hostingu/DNS strony firmy, do którego ten agent nie ma dostępu | Średnie — użytkownik wpisujący gołą domenę z wymuszonym HTTPS w przeglądarce dostanie błąd połączenia; README/RUNBOOK linkują platformę, nie stronę firmy |
| 4 | Stack platformy (React/Supabase/Vercel/...) nie zweryfikowany z kodu | Kod jest w `maskalkulator`, którego ten agent nie otwierał (poza zakresem) | Niskie — `docs/ARCHITECTURE.md` oznacza to wprost jako niezweryfikowane, nie jako fakt |

## Co NIE jest długiem (świadomie tak zostaje)
- Brak `package.json`/testów/builda — to repo nie ma kodu z założenia (patrz ADR-0001).
