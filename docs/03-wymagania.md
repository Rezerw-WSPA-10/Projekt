# Wymagania

**Wersja 0.1** · System Rezerw+WSPA

Źródła: potrzeby N-xx, ustalenia U-xx i cytaty z `docs/spotkania/wywiad-1.md`. Pole „Źródło: założenie” oznacza, że klient tego nie potwierdził (patrz „Pytania otwarte”).

---

## Potrzeby

| ID | Potrzeba | Źródło | Typ | Kto |
|---|---|---|---|---|
| N-01 | Wiedzieć, kiedy i gdzie wykładowca ma konsultacje, bez chodzenia pod drzwi sali | cytat 1, U-01 | potrzeba | Student |
| N-02 | Widzieć przy terminie godziny, wykładowcę, salę i przedmioty | U-02 | żądanie | Student |
| N-03 | Zapisać się na konsultacje, podając dane z U-03 | U-03 | żądanie | Student |
| N-04 | Nie można zapisać się na kilka terminów u jednego wykładowcy | U-04 | żądanie | Student |
| N-05 | Dostać potwierdzenie zapisu i powiadomienie przy zmianie sali | U-05, cytat 2 | żądanie | Student |
| N-06 | Zrezygnować z konsultacji jednym kliknięciem, w dowolnym momencie | U-06, cytat 3 | żądanie | Student |
| N-07 | Gdy brak miejsc, dostać propozycję najbliższych wolnych terminów | U-07, cytat 4 | żądanie | Student |
| N-08 | Widzieć zapisanych w kalendarzu, z listą studentów i godzin | U-08 | rozwiązanie | Wykładowca |
| N-09 | Brak przypomnień przed konsultacją | U-09 | żądanie | Student |

---

## Wymagania funkcjonalne (FR)

| ID | Treść | Źródło | Priorytet | Uwagi |
|---|---|---|---|---|
| FR-01 | System wyświetla studentowi listę terminów konsultacji wykładowcy wraz z godzinami. | N-01 | Must | |
| FR-02 | System wyświetla przy terminie imię i nazwisko wykładowcy, salę oraz przedmioty, których uczy wykładowca. | N-02 | Should | |
| FR-03 | System umożliwia studentowi zapis na termin konsultacji po podaniu imienia, nazwiska, kierunku, godziny i numeru indeksu. | N-03 | Must | BR-04 |
| FR-04 | System odrzuca zapis studenta na drugi termin tego samego wykładowcy. | N-04 | Must | BR-01 |
| FR-05 | System wysyła studentowi potwierdzenie zapisu z salą, datą oraz imieniem i nazwiskiem wykładowcy. | N-05 | Must | |
| FR-06 | System wysyła studentowi powiadomienie o zmianie sali konsultacji. | N-05 | Should | BR-05 |
| FR-07 | System umożliwia studentowi rezygnację z zapisu jednym kliknięciem. | N-06 | Must | BR-03 |
| FR-08 | System blokuje zapis na termin, na którym nie ma wolnych miejsc, i informuje o tym studenta. | N-07 | Must | BR-02 |
| FR-09 | System proponuje studentowi najbliższe wolne terminy, gdy wybrany termin jest pełny. | N-07 | Should | |
| FR-10 | System wyświetla wykładowcy kalendarz, w którym po kliknięciu dnia widać listę zapisanych studentów i godzin. | N-08 | Must | |
| FR-11 | System umożliwia wykładowcy zdefiniowanie podziału godzin konsultacji. | N-01 | Must | założenie, Q-05 |
| FR-12 | System umożliwia wykładowcy zmianę sali konsultacji. | N-05 | Should | założenie, Q-04 |
| FR-13 | System umożliwia studentowi wyszukanie wykładowcy po nazwisku. | N-01 | Could | założenie |
| FR-14 | System umożliwia administratorowi zakładanie i blokowanie kont użytkowników. | karta projektu | Should | założenie |

---

## Wymagania niefunkcjonalne (NFR)

Wartości oznaczone „propozycja” są naszą propozycją do potwierdzenia z klientem.

| ID | Kategoria (ISO/IEC 25010) | Treść: miara, próg, warunki, sprawdzenie | Źródło | Priorytet |
|---|---|---|---|---|
| NFR-01 | użyteczność | Rezygnacja z zapisu wymaga jednego kliknięcia. Sprawdzenie: test ręczny scenariusza rezygnacji. | U-06, cytat 3 | Must |
| NFR-02 | użyteczność | Student bez instrukcji zapisuje się na konsultacje w czasie krótszym niż 3 minuty. Sprawdzenie: test z 5 osobami (propozycja). | N-03 | Should |
| NFR-03 | wydajność | Lista terminów wyświetla się w czasie krótszym niż 2 s dla 95% zapytań przy 100 jednoczesnych użytkownikach. Sprawdzenie: test obciążeniowy (propozycja). | N-01 | Should |
| NFR-04 | bezpieczeństwo | Listę zapisanych na termin widzi tylko wykładowca tego terminu. Sprawdzenie: próba dostępu z konta innego użytkownika kończy się odmową (propozycja). | U-08 | Must |
| NFR-05 | ochrona danych | System przechowuje wyłącznie dane z U-03: imię, nazwisko, kierunek, numer indeksu. Sprawdzenie: przegląd modelu danych. | U-03 | Must |
| NFR-06 | niezawodność | Dostępność 99% w dni robocze 7:00–21:00. Sprawdzenie: monitoring przez semestr (propozycja). | założenie | Could |
| NFR-07 | przenośność | System działa w przeglądarkach Chrome, Firefox i Edge, od szerokości ekranu 360 px. Sprawdzenie: test ręczny (propozycja). | założenie | Should |

---

## Reguły biznesowe (BR)

| ID | Treść | Źródło |
|---|---|---|
| BR-01 | Student może mieć tylko jeden zapis u jednego wykładowcy. | U-04 |
| BR-02 | Gdy na terminie nie ma wolnych miejsc, zapis na ten termin jest niemożliwy. | U-07 |
| BR-03 | Student może zrezygnować z zapisu w dowolnym momencie. | U-06, Q-06 |
| BR-04 | Zapis wymaga podania imienia, nazwiska, kierunku, godziny i numeru indeksu. | U-03 |
| BR-05 | O zmianie sali student zapisany na termin musi zostać powiadomiony. | U-05 |
| BR-06 | Lista rezerwowa nie jest stosowana. | U-07 |

---

## Ograniczenia

| ID | Treść | Źródło |
|---|---|---|
| OG-01 | Dane osobowe studentów (w tym numer indeksu) podlegają ochronie wg RODO. | przepisy prawa |
| OG-02 | Powiadomienia są wysyłane przez serwer poczty uczelni. | karta projektu, diagram kontekstu |

---

## Historyjki użytkownika

### US-01: Zapis na konsultacje (Must)

**Jako** student **chcę** zapisać się na konsultacje u wykładowcy, **aby** mieć pewność, że wykładowca mnie przyjmie.

Powiązane: N-03, N-04, N-07, FR-03, FR-04, FR-08, BR-01, BR-02, BR-04

- **Scenariusz 1: zapis poprawny**
  - **Given** termin wykładowcy ma wolne miejsce, a ja nie mam zapisu u tego wykładowcy
  - **When** podaję imię, nazwisko, kierunek, godzinę i numer indeksu i zatwierdzam zapis
  - **Then** zapis zostaje zapisany, a ja widzę potwierdzenie z salą, datą i nazwiskiem wykładowcy

- **Scenariusz 2: drugi zapis u tego samego wykładowcy**
  - **Given** mam już zapis na termin tego wykładowcy
  - **When** próbuję zapisać się na inny jego termin
  - **Then** system odrzuca zapis z informacją, że mam już zapis u tego wykładowcy (BR-01)

- **Scenariusz 3: brak wolnych miejsc**
  - **Given** wybrany termin nie ma wolnych miejsc
  - **When** próbuję zapisać się na ten termin
  - **Then** system odmawia zapisu i proponuje najbliższe wolne terminy (BR-02)

### US-02: Rezygnacja z zapisu (Must)

**Jako** student **chcę** zrezygnować z zapisu na konsultacje, **aby** nie zajmować miejsca, gdy nie przyjdę.

Powiązane: N-06, FR-07, BR-03, NFR-01

- **Scenariusz 1: rezygnacja**
  - **Given** mam aktywny zapis na konsultacje
  - **When** klikam „Rezygnuję”
  - **Then** mój zapis zostaje usunięty, a miejsce jest znów wolne

- **Scenariusz 2: cudzy zapis**
  - **Given** inny student ma zapis na ten sam termin
  - **When** próbuję zrezygnować z jego zapisu
  - **Then** system odmawia, bo mogę zrezygnować tylko z własnego zapisu

### US-03: Kalendarz zapisanych (Must)

**Jako** wykładowca **chcę** widzieć w kalendarzu zapisanych studentów, **aby** wiedzieć, kto przyjdzie na konsultacje.

Powiązane: N-08, FR-10, NFR-04

- **Scenariusz 1: lista dnia**
  - **Given** na wtorek jest zapisanych troje studentów na moje terminy
  - **When** klikam ten dzień w kalendarzu
  - **Then** widzę listę tych studentów wraz z godzinami

- **Scenariusz 2: cudze terminy**
  - **Given** inny wykładowca ma zapisanych studentów
  - **When** próbuję otworzyć listę jego terminu
  - **Then** system odmawia dostępu (NFR-04)

---

## Podsumowanie MoSCoW

| Priorytet | FR |
|---|---|
| Must (8 z 14 = 57%) | FR-01, FR-03, FR-04, FR-05, FR-07, FR-08, FR-10, FR-11 |
| Should | FR-02, FR-06, FR-09, FR-12, FR-14 |
| Could | FR-13 |
| Won't (now) | przypomnienia przed konsultacją (U-09), lista rezerwowa (BR-06) |

---

## Pytania otwarte

| ID | Pytanie | Issue |
|---|---|---|
| Q-01 | Czy cel wizyty jest obowiązkowy przy zapisie? | #1 |
| Q-02 | Czy jest limit miejsc na terminie i kto go ustala? | #2 |
| Q-03 | Co z zapisami, gdy wykładowca odwoła konsultacje? | #3 |
| Q-04 | Czy konsultacje w sprawie pracy dyplomowej wymagają zatwierdzenia? Kto zmienia salę? | #4 |
| Q-05 | Kto i jak wprowadza podział godzin do systemu? | do zgłoszenia |
| Q-06 | Czy można zrezygnować z konsultacji, która już się rozpoczęła? | do zgłoszenia |
| Q-07 | Jak student loguje się do systemu? | do zgłoszenia |
