# P-02 TO-BE: Zmiana sali konsultacji

Źródło: wywiad-1, U-05, cytat 2.

| Krok | Tor | Typ | Wymagania |
|---|---|---|---|
| Start: „Wykładowca zmienia salę” | Wykładowca | zdarzenie początkowe | N-05 |
| P-02.1 Wskaż nową salę | Wykładowca | zadanie użytkownika | FR-12 |
| P-02.2 Zapisz zmianę sali | System | zadanie usługi | FR-12 |
| P-02.3 Wyślij powiadomienie zapisanym studentom | System | zadanie usługi | FR-06, BR-05, OG-02 |
| Koniec: „Sala zmieniona, studenci powiadomieni” | System | zdarzenie końcowe | |

## Wyjątki

| ID | Wyjątek | Gdzie | Reguła |
|---|---|---|---|
| W-05 | Brak zapisanych studentów | P-02.3 | powiadomienia nie są wysyłane |
| W-06 | Zmiana sali tuż przed konsultacją | P-02.1 | brak reguły, Q-04 |
| W-07 | Serwer poczty niedostępny | P-02.3 | brak reguły, Q-08 |
