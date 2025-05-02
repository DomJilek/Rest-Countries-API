#  Testovací scénář – API informace o zemích

##  Cíl testování

Ověřit správnost a úplnost odpovědi REST API při dotazování na konkrétní země (např. Francie, Polsko) i na celý seznam států (`/all`). Testy se zaměřují na status kód, název země, vlajku, měnu a strukturu JSON dat.

---

##  Testované endpointy

- `GET https://restcountries.com/v3.1/name/france`
- `GET https://restcountries.com/v3.1/name/poland`
- `GET https://restcountries.com/v3.1/all`

---

##  Testovací kroky a očekávané výsledky

| Krok | Popis | Očekávaný výsledek |
|------|-------|----------------------|
| 1 | Odeslat požadavek na `/name/france` | HTTP 200 |
| 2 | Ověřit název země | `name.common` = `France` |
| 3 | Ověřit vlajku | `flag` = `🇫🇷` |
| 4 | Odeslat požadavek na `/name/poland` | HTTP 200 |
| 5 | Ověřit název země | `name.common` = `Poland` |
| 6 | Ověřit vlajku | `flag` = `🇵🇱` |
| 7 | Ověřit název měny | `currencies.PLN.name` = `Polish złoty` |
| 8 | Ověřit strukturu objektu | `name` má vlastnost `common` |
| 9 | `name.common` není prázdný | Hodnota není `null` ani prázdný string |
| 10 | Odeslat požadavek na `/all` | HTTP 200 a seznam více než 200 států |

---

##  Postup použití kolekce v Postmanu

1. Otevři [Postman](https://www.postman.com/)
2. Vytvoř novou kolekci a pojmenuj ji např. `Countries API Tests`
3. Přidej tři požadavky:
   - `GET https://restcountries.com/v3.1/name/france`
   - `GET https://restcountries.com/v3.1/name/poland`
   - `GET https://restcountries.com/v3.1/all`
4. Do záložky **Tests** každého požadavku vlož odpovídající testy (viz níže)
5. Spusť testy jednotlivě nebo pomocí Collection Runneru
6. Sleduj výsledky – zelené = úspěšné testy 

---

## 🛠 Nástroje

- Postman (lokálně nebo webová verze)
- JavaScript testy v záložce **Tests**


---
# Testovací scénář – API informace o zemích

## Cíl testování

Ověřit správnost a úplnost odpovědi REST API při dotazování na konkrétní země (např. Francie, Polsko) i na celý seznam států (`/all`). Testy se zaměřují na status kód, název země, vlajku, měnu a strukturu JSON dat.

---

## Testy pro Francii (`/name/france`)

### Status kód je 200
Ověřte, že odpověď má status kód 200.

### Jméno země je 'France'
Ověřte, že jméno země (`name.common`) je "France".

### Vlajka je 'Francie'
Ověřte, že vlajka (`flag`) je "Francie".

---

## Testy pro Polsko (`/name/poland`)

### Status kód je 200
Ověřte, že odpověď má status kód 200.

### Jméno země je 'Poland'
Ověřte, že jméno země (`name.common`) je "Poland".

### Vlajka je 'Polsko'
Ověřte, že vlajka (`flag`) je "Polsko".

### Název měny je 'Polish złoty'
Ověřte, že název měny (`currencies.PLN.name`) je "Polish złoty".

---

## Testy pro všechny státy (`/all`)

### Pole `common` existuje
Ověřte, že objekt `name` obsahuje vlastnost `common`.

### Pole `common` je vyplněno
Ověřte, že hodnota `name.common` není prázdná.

---

