# ADR-001: Narzędzia pracy projektowej

**Status:** przyjęta
**Data:** 2026-10-17
**Autorzy:** Vladyslav Liudvichuk, Vitalii Panko

## Kontekst

Zespół składa się z dwóch osób i realizuje projekt „System obsługi konsultacji
wykładowców (Rezerw+WSPA)". Pracujemy zarówno na zajęciach, jak i zdalnie.
Mamy podstawowe doświadczenie z Git i GitHub. Wymagania przedmiotu: dokumentacja
przechowywana w repozytorium oraz dostępność narzędzi w semestrze 2.

Kryteria i ich wagi (1 — mało ważne, 3 — bardzo ważne):

| Kryterium | Waga |
|---|---|
| koszt i licencja | 3 |
| integracja z repozytorium | 3 |
| praca wielu osób jednocześnie | 3 |
| wersjonowanie, historia zmian | 2 |
| próg wejścia (czas nauki) | 2 |
| eksport / przenośność danych | 2 |
| dostępność w semestrze 2 | 2 |

## Rozważane opcje

Oceny w skali 1–5. Suma ważona = suma (waga × ocena).

### Obszar: zarządzanie zadaniami

| Kryterium | Waga | GitHub Projects | Trello |
|---|---|---|---|
| koszt i licencja | 3 | 5 | 4 |
| integracja z repozytorium | 3 | 5 | 2 |
| próg wejścia | 2 | 4 | 5 |
| **Suma ważona** | | **38** | **28** |

### Obszar: diagramy UML / BPMN

| Kryterium | Waga | Mermaid | draw.io (diagrams.net) |
|---|---|---|---|
| wersjonowanie, historia zmian | 2 | 5 | 3 |
| integracja z repozytorium | 3 | 5 | 4 |
| próg wejścia | 2 | 3 | 5 |
| **Suma ważona** | | **31** | **28** |

### Obszar: model danych

| Kryterium | Waga | dbdiagram.io | MySQL Workbench |
|---|---|---|---|
| koszt i licencja | 3 | 4 | 5 |
| próg wejścia | 2 | 5 | 3 |
| eksport / przenośność danych | 2 | 4 | 3 |
| **Suma ważona** | | **30** | **27** |

### Obszar: projekt interfejsu

| Kryterium | Waga | Figma | Penpot |
|---|---|---|---|
| koszt i licencja | 3 | 4 | 5 |
| próg wejścia | 2 | 5 | 4 |
| eksport / przenośność danych | 2 | 3 | 4 |
| **Suma ważona** | | **28** | **31** |

## Decyzja

| Obszar | Narzędzie | Format plików w repozytorium |
|---|---|---|
| repozytorium | GitHub (Git) | — |
| zadania | GitHub Projects | zadania jako Issues; tablica dostępna przez link w README |
| dokumentacja | Markdown | pliki `.md` |
| diagramy UML / BPMN | Mermaid | blok `mermaid` w pliku `.md` |
| model danych | dbdiagram.io | plik `.dbml` + eksport PNG |
| interfejs | Penpot | link do projektu + eksport PNG/SVG w `docs/diagramy/` |
| komunikacja | Discord | — (ustalenia ze spotkań zapisujemy w `docs/spotkania/`) |

Narzędzia open source: Git, Markdown, Mermaid, Penpot.

## Konsekwencje

Co zyskujemy:
- Cała dokumentacja i diagramy są w repozytorium, a historia zmian pokazuje wkład każdej osoby.
- Diagramy w Mermaid są zwykłym tekstem, więc łatwo je wersjonować i przeglądać w pull requestach.
- Zadania są powiązane z repozytorium (Issues, commity).

Co tracimy / jakie są ryzyka:
- Mermaid ma ograniczone możliwości przy bardzo złożonych diagramach (np. rozbudowane diagramy BPMN).
- dbdiagram.io ma ograniczenia darmowego planu, a plik `.dbml` trzeba ręcznie synchronizować z eksportem PNG.
- Projekty Penpot nie są przechowywane w repozytorium, tylko jako link i eksport, więc mogą się rozjechać z aktualną wersją.

Co musimy zrobić:
- Vitalii przygotuje krótką instrukcję pracy z Mermaid i Penpot dla zespołu.
- Vladyslav skonfiguruje tablicę GitHub Projects i doda prowadzącego do repozytorium.
- Przed semestrem 2 sprawdzimy aktualne warunki planów darmowych (dbdiagram.io, Penpot).
