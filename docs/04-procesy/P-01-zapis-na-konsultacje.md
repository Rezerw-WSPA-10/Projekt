# P-01 TO-BE: Zapis na konsultacje

Źródło diagramu: `P-01-zapis-na-konsultacje.bpmn`, eksport: `P-01-zapis-na-konsultacje.svg`

![Diagram P-01](P-01-zapis-na-konsultacje.svg)

## Kroki i wymagania

| Krok | Tor | Typ | Wymagania |
|---|---|---|---|
| P-01.1 Przeglądaj terminy wykładowcy | Student | zadanie użytkownika | FR-01, FR-02, FR-13 |
| P-01.2 Wybierz termin i podaj dane | Student | zadanie użytkownika | FR-03, BR-04 |
| P-01.3 Sprawdź reguły zapisu | System | zadanie usługi | FR-04, FR-08, BR-01, BR-02 |
| P-01.4 Zapisz studenta na termin | System | zadanie usługi | FR-03 |
| P-01.5 Wyślij potwierdzenie | System | zadanie usługi | FR-05, OG-02 |
| P-01.6 Odrzuć zapis i podaj powód | System | zadanie usługi | FR-15 |
| P-01.7 Zaproponuj najbliższe terminy | System | zadanie usługi | FR-09 |

## Wyjątki

| ID | Wyjątek | Gdzie | Reguła |
|---|---|---|---|
| W-01 | Student ma już zapis u tego wykładowcy | P-01.3 | BR-01 |
| W-02 | Termin nie ma wolnych miejsc | P-01.3 | BR-02, propozycja terminów (FR-09) |
| W-03 | Brak wymaganych danych (np. numeru indeksu) | P-01.2 | BR-04 |
| W-04 | Serwer poczty nie przyjmuje wiadomości | P-01.5 | brak reguły, Q-08 |

## Koniec procesu

- „Student zapisany”
- „Zapis odrzucony”
