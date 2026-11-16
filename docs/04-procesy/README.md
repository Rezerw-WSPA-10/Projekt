# Procesy biznesowe — Rezerw+WSPA

**Wersja:** 0.1

## Lista procesów

| ID | Proces | Rodzaj | Pliki |
|---|---|---|---|
| P-00 | Umawianie konsultacji (stan obecny) | AS-IS | [opis](P-00-konsultacje-as-is.md) · [BPMN](P-00-konsultacje-as-is.bpmn) · [SVG](P-00-konsultacje-as-is.svg) |
| P-01 | Zapis studenta na konsultacje (proces główny) | TO-BE | [opis](P-01-zapis-na-konsultacje.md) · [BPMN](P-01-zapis-na-konsultacje.bpmn) · [SVG](P-01-zapis-na-konsultacje.svg) |
| P-02 | Zarządzanie terminami konsultacji przez wykładowcę | TO-BE | [opis](P-02-zarzadzanie-terminami.md) · [BPMN](P-02-zarzadzanie-terminami.bpmn) · [SVG](P-02-zarzadzanie-terminami.svg) |

Powiązanie: P-02 (odwołanie terminu, krok P-02.9) wywołuje w P-01 zdarzenie „Wykładowca odwołał termin”.

## Konwencje

- Notacja: **BPMN 2.0**. Plik źródłowy `.bpmn` otwieramy w [bpmn.io](https://demo.bpmn.io) (*Open* → wybierz plik) albo w Camunda Modeler; obok leży eksport `.svg`, który GitHub wyświetla bez instalowania narzędzi.
- Po każdej zmianie diagramu eksportujemy `.svg` ponownie — oba pliki zmieniamy w jednym PR.
- Jedna pula „Uczelnia”; tory = **role** ze słownika (Student, Wykładowca) + tor **„System Rezerw+WSPA”**.
- Systemy zewnętrzne (Serwer poczty uczelni) — osobne pule zwinięte, połączone przepływem wiadomości (linia przerywana).
- Numeracja kroków: `P-01.5` = proces P-01, krok 5. Te numery trafiają do kolumny „Proces” w [macierzy śledzenia](../macierz-sledzenia.md).
- Nazwa zadania: czasownik + rzeczownik; bez szczegółów interfejsu („kliknij”, „wpisz w pole”).

## Legenda

| Symbol | Znaczenie |
|---|---|
| cienki okrąg | zdarzenie początkowe |
| gruby okrąg | zdarzenie końcowe — osobne dla każdego wyniku |
| okrąg z zegarem / kopertą | zdarzenie czasowe / wiadomości |
| zadanie z ikoną osoby | zadanie użytkownika (człowiek pracuje w systemie) |
| zadanie z ikoną koła zębatego | zadanie usługi (system sam) |
| zadanie z ikoną dłoni | zadanie ręczne (człowiek bez systemu) |
| romb z „X” | bramka XOR — jedna ścieżka; każde wyjście podpisane |
| romb z pięciokątem | bramka oparta na zdarzeniach — wygrywa pierwsze zdarzenie |
| czerwone wypełnienie (P-00) | **punkt bólu** — tu system zmienia proces |
