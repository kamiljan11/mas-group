# RUNBOOK — operacje i awarie

Ten repo nie hostuje niczego — jest dokumentacją. "Awaria" tutaj oznacza awarię PLATFORMY
(`masgroup.is`), nie tego repo. To repo samo w sobie nie może "spaść".

## Podstawy
- Produkcja: https://www.masgroup.is (UWAGA: `https://masgroup.is` bez `www` nie odpowiada — brak nasłuchu HTTPS na apeksie, zweryfikowane `curl -v`)
- Kod aplikacji: osobne repo [`maskalkulator`](https://github.com/kamiljan11/maskalkulator) (patrz README → Source)
- Ten repo: github.com/kamiljan11/mas-group (tylko dokumentacja)
- Sekrety: nie dotyczy tego repo (brak kodu, brak env)

## Deploy
Nie dotyczy tego repo. Deploy platformy opisany (jeśli w ogóle) w `maskalkulator`.

## Healthcheck
```bash
curl -I https://www.masgroup.is   # 200 = platforma wstaje
curl -I https://masgroup.is       # oczekiwany timeout/redirect — NIE traktuj jako awarię platformy
```

## Typowe awarie
| Objaw | Pierwszy krok |
|---|---|
| `www.masgroup.is` nie odpowiada | Sprawdz hosting/DNS platformy — poza tym repo. Zacznij od `maskalkulator`. |
| Ktoś zgłasza, że "masgroup.is nie działa" (bez www) | To znany, opisany stan apeksu (brak HTTPS) — nie panikuj, ale rozważ naprawę certyfikatu/redirectu po stronie hostingu |
| Ktoś pyta o kod/logikę cenową/prowizje | Nie tutaj — skieruj do `maskalkulator`, sprawdź czy ma dostęp |

## Kontakty
- Właściciel: Kamil Jan, mountainallservice@gmail.com
