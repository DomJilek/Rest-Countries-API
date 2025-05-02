# Testy pro API Informace o Zemích

## Cíl testování
Ověřit správnost a úplnost odpovědi REST API při dotazování na konkrétní země (např. Francie, Polsko) i na celý seznam států (`/all`). Testy se zaměřují na status kód, název země, vlajku, měnu a strukturu JSON dat.

---

## Testy

### 1. Testy pro Francii (`/name/france`)

- **Status kód je 200**  
  Ověřte, že odpověď má status kód 200.

- **Jméno země je 'France'**  
  Ověřte, že jméno země (`name.common`) je "France".

- **Vlajka je '🇫🇷'**  
  Ověřte, že vlajka (`flag`) je "🇫🇷".

### 2. Testy pro Polsko (`/name/poland`)

- **Status kód je 200**  
  Ověřte, že odpověď má status kód 200.

- **Jméno země je 'Poland'**  
  Ověřte, že jméno země (`name.common`) je "Poland".

- **Vlajka je '🇵🇱'**  
  Ověřte, že vlajka (`flag`) je "🇵🇱".

- **Název měny je 'Polish złoty'**  
  Ověřte, že název měny (`currencies.PLN.name`) je "Polish złoty".

### 3. Testy pro Všechny země (`/name/all`)

- **Pole common existuje**  
  Ověřte, že objekt `name` obsahuje vlastnost `common`.

- **Pole common je vyplněno**  
  Ověřte, že hodnota `name.common` není prázdná.
