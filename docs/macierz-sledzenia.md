# Macierz śledzenia

**Wersja 0.2** · Jeden wiersz = jedno wymaganie. Pusta komórka lub „—” oznacza pytanie do uzupełnienia.

| Potrzeba | Wymaganie | Historyjka | Priorytet | Proces |
|---|---|---|---|---|
| N-01 | FR-01 Lista terminów wykładowcy | — | Must | P-01.1 |
| N-01 | FR-11 Definiowanie podziału godzin | US-04 | Must | P-02.3, P-02.4 |
| N-01 | FR-13 Wyszukiwanie wykładowcy | — | Could | P-01.1 |
| N-02 | FR-02 Szczegóły terminu | — | Should | P-01.1 |
| N-03 | FR-03 Zapis na konsultacje | US-01 | Must | P-01.2, P-01.4 |
| N-03 | BR-04 Dane wymagane przy zapisie | US-01 | Must | P-01.2, P-01.3 |
| N-04 | FR-04 Odrzucenie drugiego zapisu | US-01 | Must | P-01.3 |
| N-04 | BR-01 Jeden zapis u jednego wykładowcy | US-01 | Must | P-01.3 |
| N-05 | FR-05 Potwierdzenie zapisu | US-01 | Must | P-01.5 |
| N-05 | FR-06 Powiadomienie o zmianie sali | — | Should | P-02.7 |
| N-05 | FR-12 Zmiana sali przez wykładowcę | — | Should | P-02.6 |
| N-05 | BR-05 Obowiązek powiadomienia o zmianie sali | — | Should | P-02.7 |
| N-06 | FR-07 Rezygnacja jednym kliknięciem | US-02 | Must | P-03.2, P-03.3 |
| N-06 | BR-03 Rezygnacja w dowolnym momencie | US-02 | Must | P-03.2 |
| N-07 | FR-08 Blokada zapisu bez miejsc | US-01 | Must | P-01.3 |
| N-07 | FR-09 Propozycja najbliższych terminów | US-01 | Should | P-01.7 |
| N-07 | BR-02 Brak miejsc blokuje zapis | US-01 | Must | P-01.3 |
| N-08 | FR-10 Kalendarz z listą zapisanych | US-03 | Must | P-02.5 |
| N-09 | BR-06 Brak listy rezerwowej | — | Won't | — (brak listy rezerwowej; zamiast niej P-01.7) |
| karta projektu | FR-14 Zarządzanie kontami | — | Should | — (funkcja administracyjna; brak procesu „zarządzanie kontami” — do decyzji) |
| N-04, N-07 | FR-15 Odrzucenie zapisu z podaniem powodu | US-01 | Must | P-01.6 |
| karta projektu | FR-16 Logowanie | US-05 | Must | P-02.1, P-03.1 |
| karta projektu | FR-17 Odwołanie terminu przez wykładowcę | — | Should | P-02.8 |
| N-07 | FR-18 Limit miejsc na termin | US-04 | Must | P-02.3 |
| karta projektu | FR-19 Powiadomienie o odwołaniu terminu | — | Should | P-02.9 |
| — (walkthrough) | BR-07 Terminy wykładowcy się nie nakładają | US-04 | Must | P-02.4 |
| karta projektu | BR-08 Odwołanie anuluje zapisy i wymaga powiadomienia | — | Should | P-02.9 |

Kolumna „Proces” (od wersji 0.2): krok procesu TO-BE z `docs/04-procesy/`, np. `P-01.6` = proces P-01, krok 6. „—” = wymaganie bez kroku procesu (wyjaśnienie w nawiasie).

Łańcuch wzorcowy: **FR-07 → US-02 → P-03.2 / P-03.3** → (zaj. 7) przypadek użycia → … → test.
