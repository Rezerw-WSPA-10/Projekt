# Projekt zespołowy systemu informatycznego cz. 1
## Materiały do zajęć 1

---

# A. Karta projektu

## KARTA PROJEKTU — WERSJA 0.1

### 1. Podstawowe informacje

**Nazwa projektu:**

System obsługi konsultacji wykładowców

**Krótka nazwa / akronim:**

Rezerw+WSPA

**Zespół:**

| Imię i nazwisko     | Rola główna                     | Kontakt / login repozytorium |
| ------------------- | ------------------------------- | ---------------------------- |
| Vladyslav Liudvichuk| Programista Backend / Bazy Danych|                              |
| Vitalii Panko       | Programista Frontend / UI/UX    |                              |
|                     |                                 |                              |

---

## 2. Problem

### Jaki problem chcemy rozwiązać?
Obecnie proces umawiania się na konsultacje z wykładowcami jest nieefektywny i rozproszony. Studenci często muszą wysyłać wielokrotne wiadomości e-mail, aby ustalić wolny termin, co prowadzi do chaosu informacyjnego i nakładania się wizyt. Wykładowcy nie mają jednolitego narzędzia do zarządzania swoim harmonogramem konsultacji oraz listą zapisanych osób. Brakuje również szybkiego sposobu na powiadamianie studentów o odwołaniu lub przesunięciu terminu konsultacji.

---

## 3. Kogo dotyczy problem?
Problem dotyczy studentów wszystkich kierunków i trybów studiów oraz nauczycieli akademickich (wykładowców), którzy prowadzą regularne lub dodatkowe konsultacje.

---

## 4. Cel systemu

Celem systemu jest usprawnienie i automatyzacja procesu rezerwacji oraz zarządzania terminami konsultacji akademickich poprzez udostępnienie dedykowanej platformy internetowej dla studentów i wykładowców.

---

## 5. Użytkownicy systemu

| Użytkownik / rola   | Do czego będzie używał systemu? |
| ------------------- | ------------------------------- |
| Student             | Do wyszukiwania wykładowców, rezerwacji wolnych terminów konsultacji oraz anulowania swoich zapisów. |
| Wykładowca          | Do definiowania harmonogramu konsultacji, określania limitu miejsc oraz zarządzania listą zapisanych studentów. |
| Administrator       | Do zarządzania kontami użytkowników oraz słownikami systemowymi (np. jednostki organizacyjne, przedmioty). |

---

## 6. Interesariusze

| Interesariusz             | Dlaczego system jest dla niego istotny? |
| ------------------------- | --------------------------------------- |
| Studenci                  | Oszczędność czasu i pewność, że wybrany termin konsultacji jest aktualny i zarezerwowany. |
| Wykładowcy                | Porządek w harmonogramie pracy i redukcja niepotrzebnej korespondencji mailowej. |
| Władze uczelni / Wydział  | Poprawa jakości obsługi studentów oraz przejrzystość dostępności kadry dydaktycznej. |

---

## 7. Zakres IN

Co system **będzie** realizował?

1. Rejestrację i logowanie użytkowników z podziałem na role (Student, Wykładowca, Admin).
2. Tworzenie, edycję i usuwanie terminów konsultacji przez wykładowców.
3. Wyszukiwanie wykładowców oraz przeglądanie ich dostępnych terminów.
4. Rezerwację wybranego terminu konsultacji przez studenta.
5. Anulowanie rezerwacji przez studenta lub wykładowcę.
6. Podgląd listy zapisanych studentów na dany termin przez wykładowcę.
7. System powiadomień e-mail / w aplikacji o zmianie lub odwołaniu konsultacji.

---

## 8. Zakres OUT

Czego system **nie będzie** realizował?

1. Prowadzenia wideokonferencji / rozmów wideo na żywo wewnątrz aplikacji (integracja z MS Teams/Zoom tylko jako link zewnętrzny).
2. Oceniania i wystawiania stopni po przeprowadzonej konsultacji.
3. Importu planu zajęć bezpośrednio z zewnętrznych systemów dziekanatowych (np. USOS API).
4. Systemu płatności za konsultacje (konsultacje są bezpłatne).
5. Czatu tekstowego w czasie rzeczywistym między studentem a wykładowcą.

---

## 9. Najważniejsze funkcje

Wymieńcie maksymalnie 10 funkcji.

1. Logowanie i autoryzacja użytkowników (JWT / Session).
2. Tworzenie harmonogramu konsultacji (wybór daty, godziny, limitu osób, trybu: stacjonarny/online).
3. Rezerwacja slotu czasowego przez studenta wraz z podaniem celu wizyty.
4. Anulowanie wizyty z opcjonalnym podaniem przyczyny.
5. Przeglądanie historii oraz nadchodzących konsultacji w panelu użytkownika.
6. Wyszukiwarka wykładowców po nazwisku lub przedmiocie.
7. Automatyczne blokowanie slotu po wyczerpaniu limitu miejsc.
8. Wysyłanie powiadomień mailowych o potwierdzeniu/odwołaniu rezerwacji.

---

## 10. Główne obiekty / dane

Jakiego rodzaju informacje system prawdopodobnie będzie przechowywał?

Dla naszego systemu:

1. Użytkownik (User / Osoba - Student/Wykładowca/Admin)
2. Termin konsultacji (ConsultationSlot)
3. Rezerwacja (Booking)
4. Przedmiot / Jednostka (Subject / Department)
5. Powiadomienie (Notification)

---

## 11. Główne założenia

Zakładamy, że każdy użytkownik posiada konto w systemie z przypisaną rolą.
Zakładamy, że rezerwacja konsultacji wymaga podania tematu/sprawy przez studenta.
Zakładamy, że odwołanie konsultacji przez wykładowcę automatycznie zwalnia slot i informuje studenta.

---

## 12. Wstępne ryzyka

Co może utrudnić wykonanie projektu?

| Ryzyko                                                      | Dlaczego może być problemem? |
| ----------------------------------------------------------- | ---------------------------- |
| Nakładanie się terminów konsultacji z zajęciami dydaktycznymi | Brak integracji z planem zajęć może prowadzić do błędnego podania dostępności przez wykładowcę. |
| Brak przychodzenia studentów na zarezerwowane terminy       | Rezerwacja miejsca bez pojawienia się blokuje termin dla innych potrzebujących studentów. |

---

## 13. Wstępnie rozważane technologie

Ta część **nie jest najważniejsza na tym etapie**.

Frontend:

HTML, CSS, JS

Backend:

Python

Baza danych:

MySQL

Inne:

GitHub

---

# B. Formularz wyboru tematu

## WYBÓR TEMATU PROJEKTU

**Zespół:**

Vladyslav Liudvichuk, Vitalii Panko

### Temat 1 — preferowany

**Nazwa:**

System obsługi konsultacji wykładowców (Rezerw+WSPA)

**Problem:**

Utrudniony i nieefektywny proces umawiania konsultacji akademickich, brak przejrzystego harmonogramu dostępności wykładowców oraz chaos w komunikacji mailowej.

**Główni użytkownicy:**

Studenci, Wykładowcy

**Dlaczego chcemy realizować ten temat?**

Temat posiada jasną i przejrzystą logikę biznesową, idealną dla dwuosobowego zespołu, pozwalającą na precyzyjny podział prac na część frontendową i backendową bez zbędnego narzutu skomplikowanych modułów.

---

## Decyzja prowadzącego

- [ ] temat zaakceptowany,
- [ ] temat zaakceptowany po zmianie zakresu,
- [ ] temat wymaga ponownego opracowania.

### Uwagi

....................................................................................

---

# C. Formularz podziału ról

## ZESPÓŁ PROJEKTOWY

**Nazwa projektu:**

System obsługi konsultacji wykładowców (Rezerw+WSPA)

| Obszar odpowiedzialności | Osoba główna         | Osoba wspierająca    |
| ------------------------ | -------------------- | -------------------- |
| koordynacja projektu     | Vladyslav Liudvichuk | Vitalii Panko        |
| analiza wymagań          | Vitalii Panko        | Vladyslav Liudvichuk |
| procesy biznesowe        | Vitalii Panko        | Vladyslav Liudvichuk |
| architektura             | Vladyslav Liudvichuk | Vitalii Panko        |
| baza danych              | Vladyslav Liudvichuk | Vitalii Panko        |
| UI/UX                    | Vitalii Panko        | Vladyslav Liudvichuk |
| implementacja            | Vladyslav Liudvichuk | Vitalii Panko        |
| testowanie               | Vitalii Panko        | Vladyslav Liudvichuk |
| dokumentacja             | Vitalii Panko        | Vladyslav Liudvichuk |

---

## Zasada

Każdy członek zespołu:

- zna cały projekt,
- wykonuje zadania projektowe,
- ma przynajmniej jeden obszar głównej odpowiedzialności.

Role mogą ulegać zmianie.

---

## Koordynator zespołu

**Imię i nazwisko:**

Vladyslav Liudvichuk

Koordynator odpowiada za:

- pilnowanie terminów,
- organizację pracy,
- kontrolę tablicy zadań,
- upewnienie się, że projekt jest spójny.

Koordynator:

**nie jest przełożonym pozostałych studentów.**

---

# D. Pierwsze zadanie zespołowe

## ZADANIE 1 — OD POMYSŁU DO KARTY PROJEKTU

### Cel

Waszym zadaniem jest przygotowanie pierwszej wersji koncepcji systemu.

---

## Etap 1 — wybierzcie problem

### Co obecnie działa źle albo nieefektywnie?

Proces umawiania się na konsultacje z wykładowcami jest nieefektywny i rozproszony. Studenci wysyłają wielokrotne maile, co prowadzi do chaosu i nakładania się terminów.

### Kto doświadcza tego problemu?

Studenci wszystkich kierunków oraz nauczyciele akademiccy.

### Jak obecnie radzi sobie bez projektowanego systemu?

Ręczna komunikacja mailowa, brak centralnego harmonogramu i trudności w odwoływaniu wizyt.

---

## Etap 2 — określcie cel

> Celem projektowanego systemu jest usprawnienie i automatyzacja procesu rezerwacji oraz zarządzania terminami konsultacji akademickich poprzez udostępnienie dedykowanej platformy internetowej dla studentów i wykładowców.

---

## Etap 3 — wskażcie użytkowników

| Rola        | Potrzeba |
| ----------- | -------- |
| Student     | Wyszukiwanie wykładowców, rezerwacja wolnych terminów, anulowanie zapisów. |
| Wykładowca  | Definiowanie harmonogramu, limitów miejsc, zarządzanie listą studentów. |
| Administrator| Zarządzanie kontami użytkowników i słownikami systemowymi. |

---

## Etap 4 — określcie zakres

### IN

1. Logowanie i autoryzacja z podziałem na role.
2. Zarządzanie terminami konsultacji przez wykładowców.
3. Wyszukiwanie wykładowców i przeglądanie ich dostępności.
4. Rezerwacja terminów przez studentów.
5. System powiadomień e-mail.

### OUT

1. Prowadzenie wideokonferencji wewnątrz aplikacji.
2. Ocenianie studentów po konsultacji.
3. Import planu zajęć z USOS API.

---

## Etap 5 — określcie główne funkcje

### 3 funkcje najważniejsze

1. Tworzenie harmonogramu konsultacji przez wykładowcę.
2. Rezerwacja slotu czasowego przez studenta z podaniem celu.
3. Wysyłanie automatycznych powiadomień mailowych o zmianie lub odwołaniu rezerwacji.

### Funkcje dodatkowe

Anulowanie wizyty z podaniem przyczyny, wyszukiwarka po nazwisku/przedmiocie, blokowanie slotu po wyczerpaniu limitu.

---

## Etap 6 — podzielcie odpowiedzialność

Formularz ról został wypełniony w sekcji C.

---

## Etap 7 — przygotujcie prezentację

# 2 minuty (5 pytań)

1. **Jaki jest temat?** System obsługi konsultacji wykładowców (Rezerw+WSPA).
2. **Jaki problem rozwiązujecie?** Chaos w umawianiu konsultacji przez e-mail i brak przejrzystego harmonogramu.
3. **Kto będzie użytkownikiem?** Studenci, Wykładowcy, Administratorzy.
4. **Jakie są trzy najważniejsze funkcje?** Definiowanie terminów, rezerwacja slotów przez studentów, powiadomienia e-mail.
5. **Czego system nie będzie realizował?** Wbudowanych wideokonferencji, wystawiania ocen, integracji z USOS.

---

# E. Kryteria akceptacji zadania

Zadanie jest wykonane, jeżeli:

- [x] zespół posiada temat,
- [x] problem został opisany,
- [x] określono cel,
- [x] wskazano użytkowników,
- [x] wskazano interesariuszy,
- [x] określono zakres IN,
- [x] określono zakres OUT,
- [x] określono główne funkcje,
- [x] członkowie zespołu mają role,
- [x] karta projektu 0.1 została utworzona.

---

# F. Autokontrola zespołu

| Pytanie | TAK/NIE |
|---|---|
| Czy rozwiązujemy konkretny problem? | TAK |
| Czy potrafimy wskazać użytkowników? | TAK |
| Czy mamy więcej niż jedną rolę użytkownika? | TAK |
| Czy system zawiera rzeczywisty proces? | TAK |
| Czy system będzie przechowywał dane? | TAK |
| Czy występują reguły biznesowe? | TAK |
| Czy zakres jest możliwy do wykonania? | TAK |
| Czy wiemy, czego świadomie nie wykonujemy? | TAK |
| Czy projekt jest czymś więcej niż prostym CRUD-em? | TAK |

---

# G. Praca po pierwszych zajęciach

## Studenci stacjonarni

Do następnego spotkania przygotować:

1. kartę projektu 0.2,
2. dopracowany zakres IN/OUT,
3. listę interesariuszy,
4. minimum 10 terminów do słownika dziedzinowego,
5. repozytorium projektu.