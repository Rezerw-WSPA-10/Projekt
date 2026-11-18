# P-02: Zarządzanie terminami konsultacji (TO-BE)

**Wersja:** 0.1 · **Powiązane:** P-00 (AS-IS), P-01

## Cel procesu

Wykładowca udostępnia aktualne terminy konsultacji, a zapisani studenci wiedzą o każdej zmianie sali i o odwołaniu terminu.

## Wyzwalacz (zdarzenie początkowe)

Wykładowca planuje konsultacje (np. na początku semestru albo przy zmianie planu).

## Uczestnicy (tory i pule)

- tory: Wykładowca, System Rezerw+WSPA,
- pula zewnętrzna: Serwer poczty uczelni.

## Wyniki (zdarzenia końcowe)

- terminy aktualne (bez zmian),
- sala zmieniona (zapisani powiadomieni),
- termin odwołany (zapisy anulowane, studenci powiadomieni).

## Diagram

![P-02 Zarządzanie terminami konsultacji](P-02-zarzadzanie-terminami.svg)

Źródło: [P-02-zarzadzanie-terminami.bpmn](P-02-zarzadzanie-terminami.bpmn) (bpmn.io)

## Kroki

| Krok | Tor | Typ zadania | Opis | Wymagania |
|---|---|---|---|---|
| start | Wykładowca | zdarzenie | wykładowca planuje konsultacje | — |
| P-02.1 | Wykładowca | użytkownika | zaloguj się | FR-15 |
| P-02.2 | Wykładowca | ręczne | sprawdź swój plan zajęć (poza systemem — import planu z USOS jest w zakresie OUT) | — (OUT) |
| P-02.3 | Wykładowca | użytkownika | zdefiniuj podział godzin, salę i limit miejsc | FR-11, FR-17 |
| P-02.4 | System | usługi | sprawdź, czy terminy się nie nakładają, i opublikuj je studentom | FR-11, BR-07 |
| bramka | System | XOR | terminy poprawne? nie → P-02.3 | BR-07 |
| P-02.5 | Wykładowca | użytkownika | przejrzyj kalendarz zapisanych (dzień → lista studentów i godzin) | FR-10, NFR-04 |
| bramka | Wykładowca | XOR | potrzebna zmiana? nie / zmiana sali / odwołanie | — |
| P-02.6 | Wykładowca | użytkownika | zmień salę konsultacji | FR-12 |
| P-02.7 | System | usługi | zapisz zmianę i powiadom zapisanych studentów | FR-06, BR-05 |
| P-02.8 | Wykładowca | użytkownika | odwołaj termin | FR-16 |
| P-02.9 | System | usługi | anuluj zapisy na ten termin i powiadom studentów (zdarzenie w P-01) | FR-18, BR-08 |

## Wyjątki i ścieżki alternatywne

| Wyjątek | Gdzie | Reakcja | Wymaganie / BR |
|---|---|---|---|
| terminy wykładowcy nakładają się | P-02.4 | komunikat, powrót do P-02.3 | BR-07 |
| konsultacje kolidują z zajęciami wykładowcy | P-02.2 | sprawdzenie ręczne — system nie zna planu zajęć (ryzyko z karty projektu) | zakres OUT |
| zmiana sali po zapisach | P-02.6–P-02.7 | zapisy zostają, studenci powiadomieni | FR-06, BR-05 |
| odwołanie terminu z zapisanymi studentami | P-02.8–P-02.9 | zapisy anulowane, studenci powiadomieni | FR-16, FR-18, BR-08 |
| inny wykładowca próbuje zobaczyć listę | P-02.5 | odmowa dostępu | NFR-04 |

## Zmiany względem AS-IS

- **znika:** kartka na drzwiach z godzinami i ze zmianą sali,
- **nowe kroki:** kalendarz zapisanych (P-02.5), automatyczne powiadomienia (P-02.7, P-02.9),
- **zostaje poza systemem:** sprawdzenie planu zajęć (P-02.2) — świadoma decyzja (zakres OUT).

## Otwarte pytania

- Q-02: kto ustala limit miejsc na termin? (P-02.3)
- Q-03: co z zapisami, gdy wykładowca odwoła konsultacje? (P-02.9 — przyjęte założenie: anulowanie + powiadomienie)
- Q-08: czy odwołując termin, wykładowca musi podać przyczynę? (P-02.8)
