#  Testy pro API Informace o Zemích

##  Cíl testování
Ověřit správnost a úplnost odpovědi REST API při dotazování na konkrétní země (např. Francie, Polsko) i na celý seznam států (`/all`). Testy se zaměřují na status kód, název země, vlajku, měnu a strukturu JSON dat.

---

##  Testy 

### 1. Testy pro Francii (`/name/france`)

```javascript
// Status kód je 200
pm.test("Status kód je 200", function () {
    pm.response.to.have.status(200);
});

var jsonData = pm.response.json();

// Jméno země je 'France'
pm.test("Jméno země je 'France'", function () {
    pm.expect(jsonData[0].name.common).to.eql("France");
});

// Vlajka je '🇫🇷'
pm.test("Vlajka je '🇫🇷'", function () {
    pm.expect(jsonData[0].flag).to.eql("🇫🇷");
});

// Status kód je 200
pm.test("Status kód je 200", function () {
    pm.response.to.have.status(200);
});

var jsonData = pm.response.json();

// Jméno země je 'Poland'
pm.test("Jméno země je 'Poland'", function () {
    pm.expect(jsonData[0].name.common).to.eql("Poland");
});

// Vlajka je '🇵🇱'
pm.test("Vlajka je '🇵🇱'", function () {
    pm.expect(jsonData[0].flag).to.eql("🇵🇱");
});

// Název měny je 'Polish złoty'
pm.test("Název měny je 'Polish złoty'", function () {
    pm.expect(jsonData[0].currencies.PLN.name).to.eql("Polish złoty");
});

// Status kód je 200
pm.test("Status kód je 200", function () {
    pm.response.to.have.status(200);
});

var jsonData = pm.response.json();

// Seznam všech států obsahuje více než 200 položek
pm.test("Seznam obsahuje více než 200 států", function () {
    pm.expect(jsonData.length).to.be.above(200);
});
