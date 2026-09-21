# RUNBOOK — operacje i awarie

Ten repo nie hostuje niczego — jest dokumentacją. "Awaria" tutaj oznacza awarię PLATFORMY
(`maskalkulator.lovable.app`), nie tego repo. To repo samo w sobie nie może "spaść".

## Podstawy
- Produkcja (platforma): https://maskalkulator.lovable.app
- Strona firmy (nie platforma): https://www.masgroup.is
- Kod aplikacji: osobne repo [`maskalkulator`](https://github.com/kamiljan11/maskalkulator) (patrz README → Source)
- Ten repo: github.com/kamiljan11/mas-group (tylko dokumentacja)
- Sekrety: nie dotyczy tego repo (brak kodu, brak env)

## Deploy
Nie dotyczy tego repo. Deploy platformy opisany (jeśli w ogóle) w `maskalkulator`.

## Healthcheck
```bash
curl -I https://maskalkulator.lovable.app   # 200 = platforma wstaje
```

## Typowe awarie
| Objaw | Pierwszy krok |
|---|---|
| `maskalkulator.lovable.app` nie odpowiada | Sprawdz projekt w Lovable — poza tym repo. Zacznij od `maskalkulator`. |
| Ktoś pyta o kod/logikę cenową/prowizje | Nie tutaj — skieruj do `maskalkulator`, sprawdź czy ma dostęp |

## Kontakty
- Właściciel: Kamil Jan, mountainallservice@gmail.com
