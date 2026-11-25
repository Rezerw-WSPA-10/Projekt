# ADR-002: Modularny monolit

**Status:** zaproponowany

**Kontekst:** zespół 2 osób, małe grono użytkowników, jedna uczelniana usługa zewnętrzna (poczta), brak potrzeby niezależnego skalowania. Gotowy SaaS nie realizuje reguł z wywiadu (BR-01, BR-02).

**Opcje:**
1. monolit warstwowy
2. modularny monolit
3. mikroserwisy

**Decyzja:** SPA + backend API w modularnym monolicie + PostgreSQL (propozycja).

**Konsekwencje:**
- (+) jedno wdrożenie, reguły BR-01 i BR-02 w jednej transakcji
- (+) prostota dla małego zespołu
- (−) brak niezależnego skalowania
- (−) granice modułów trzeba pilnować
