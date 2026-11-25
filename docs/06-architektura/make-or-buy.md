# Make or buy — lista kandydatów

**Wersja:** 0.1 (wstępna; decyzje zapiszemy w ADR na zajęciach 6)

**Make** = projektujemy i (w semestrze 2) budujemy sami. **Buy** = korzystamy z gotowego rozwiązania: usługi uczelni, usługi zewnętrznej (SaaS) albo biblioteki open source — „buy” nie znaczy „płacimy”, tylko „nie projektujemy tego sami”.

Źródło kandydatów: pule zewnętrzne i zadania w procesach TO-BE (`docs/04-procesy/`).

| Funkcja / wymaganie | Gotowe rozwiązanie (kandydat) | Wstępnie | Uzasadnienie / pytanie |
|---|---|---|---|
| FR-15 Logowanie (P-01.1, P-02.1) | konto uczelniane (logowanie jednokrotne SSO, np. Microsoft 365 uczelni) **albo** własne konta + biblioteka do uwierzytelniania (np. JWT) | do decyzji | zależy od odpowiedzi na Q-07; SSO zwalnia nas z przechowywania haseł, ale wymaga zgody działu IT uczelni |
| FR-05, FR-06, FR-18 Powiadomienia e-mail (P-01.8, P-02.7, P-02.9) | serwer poczty uczelni (SMTP) + biblioteka do wysyłki e-mail | buy | pula „Serwer poczty uczelni” w P-01 i P-02 (ograniczenie OG-02); pytanie: czy uczelnia pozwala na wysyłkę z aplikacji? |
| FR-10 Kalendarz zapisanych (P-02.5) | biblioteka komponentu kalendarza (open source) | do decyzji | czy wystarczy prosta lista dni? sprawdzić licencję wybranej biblioteki (część funkcji bywa płatna) |
| Baza danych (wszystkie procesy) | gotowy system zarządzania bazą danych (MySQL — karta projektu, p. 13) | buy | nie piszemy własnego magazynu danych; wybór potwierdzimy w ADR |
| Plan zajęć wykładowcy (P-02.2) | import z USOS | **nie dotyczy** (zakres OUT) | świadomie poza systemem: wykładowca sprawdza plan ręcznie (zadanie ręczne P-02.2) |
| Konsultacje online | link do MS Teams / Zoom jako zwykłe pole tekstowe | nie dotyczy (zakres OUT) | wideokonferencja poza systemem; przechowujemy tylko link |
| FR-03, FR-04, FR-07, FR-08, FR-09 Zapis, reguły, rezygnacja, propozycja terminów (P-01.4–P-01.10) | — | **make** | rdzeń systemu, reguły BR-01…BR-04 — to odróżnia nasz system |
| FR-11, FR-12, FR-16, FR-17 Terminy, sala, limit, odwołanie (P-02.3–P-02.9) | — | **make** | rdzeń dziedziny, reguły BR-05, BR-07, BR-08 |
| FR-14 Zarządzanie kontami | konta z katalogu uczelni (jeśli SSO) albo prosty panel administratora | do decyzji | zależy od decyzji przy FR-15 |

# Make or buy

Kryteria: dopasowanie, koszt, ryzyko, zależność od dostawcy, RODO, czas. Ceny i warunki nie są tu zgadywane: do sprawdzenia przy realizacji.

| Obszar | Wymagania | Decyzja | Dopasowanie | Ryzyko / RODO / zależność |
|---|---|---|---|---|
| Cały system (gotowy SaaS do konsultacji) | FR-03, FR-04, FR-08, BR-01, BR-02 | **make** | gotowy produkt nie zna reguł z wywiadu (jeden zapis u wykładowcy, brak miejsc) | brak zależności od dostawcy; więcej pracy |
| Powiadomienia e-mail | FR-05, FR-06, OG-02 | **use**: serwer poczty uczelni, szablony wiadomości **make** | spełnia wymagania w całości | zależność od poczty uczelni (R-04); adres e-mail jest daną osobową |
| Uwierzytelnianie | FR-14, Q-07 | **make**: własne konta (zgodnie z kartą projektu) | spełnia wymagania; SSO odpada poza zakresem | przechowywanie haseł, ryzyko bezpieczeństwa (R-05); ADR-003 |
| Kalendarz wykładowcy | FR-10 | **use**: biblioteka kalendarza open source | spełnia widok dnia z listą | zależność od biblioteki; brak danych osobowych w bibliotece |
| Baza danych | wszystkie | **use**: PostgreSQL (propozycja) | spełnia w całości | open source, brak dostawcy |
| Płatności, mapy, push | | nie dotyczy | | |

## Pytania do wyjaśnienia przed zajęciami 6

- Czy uczelnia udostępnia logowanie kontem uczelnianym dla aplikacji studenckich? (Q-07)
- Czy można wysyłać e-maile z aplikacji przez serwer poczty uczelni, czy potrzebna jest zewnętrzna usługa?
- Czy kalendarz wykładowcy (FR-10) musi być widokiem miesiąca/tygodnia, czy wystarczy lista dni?
