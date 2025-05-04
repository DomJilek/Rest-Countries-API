
##  Testy 

### 1. Testy pro Francii (/name/france)

javascript
// Status kód je 200
pm.test("Status kód je 200", function () {
    pm.response.to.have.status(200);
});


// Jméno země je 'France'
pm.test("Jméno země je 'France'", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[0].name.common).to.eql("France");
});

// Vlajka je '🇫🇷'
pm.test("Vlajka je '🇫🇷'", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[0].flag).to.eql("🇫🇷");
});

### 2. Testy pro Polsko (`/name/poland`)

// Status kód je 200
pm.test("Status kód je 200", function () {
    pm.response.to.have.status(200);
});


// Jméno země je 'Poland'
pm.test("Jméno země je 'Poland'", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[0].name.common).to.eql("Poland");
});

// Vlajka je '🇵🇱'
pm.test("Vlajka je '🇵🇱'", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[0].flag).to.eql("🇵🇱");
});

// Název měny je 'Polish złoty'
pm.test("Název měny je 'Polish złoty'", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[0].currencies.PLN.name).to.eql("Polish złoty");
});

### 3. Testy pro Všechny země (`/name/all`)

// Pole common existuje.
pm.test("Pole common existuje.", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData[0].name).to.have.property("common");  // Ověří, že objekt 'name' má vlastnost 'common'
});