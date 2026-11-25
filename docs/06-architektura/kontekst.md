# C4 poziom 1: kontekst systemu

```mermaid
flowchart LR
    S(["Student<br/>[osoba]"])
    W(["Wykładowca<br/>[osoba]"])
    A(["Administrator<br/>[osoba]"])
    RW["Rezerw+WSPA<br/>[system]"]
    E["Serwer poczty uczelni<br/>[system zewnętrzny]"]
    S -->|"przegląda terminy, zapisuje się i rezygnuje"| RW
    W -->|"definiuje terminy, przegląda zapisanych, zmienia salę"| RW
    A -->|"zarządza kontami i słownikami"| RW
    RW -->|"wysyła potwierdzenia i powiadomienia [SMTP]"| E
```

## Opis elementów

| Element | Typ | Opis | Właściciel / dane |
|---|---|---|---|
| Student | osoba | Zapisuje się na konsultacje i rezygnuje z nich. | imię, nazwisko, kierunek, numer indeksu |
| Wykładowca | osoba | Ustala terminy i sale, widzi listę zapisanych. | imię, nazwisko, terminy, przedmioty |
| Administrator | osoba | Zakłada i blokuje konta, uzupełnia słowniki. | konta użytkowników |
| Rezerw+WSPA | system | Platforma zapisów na konsultacje. | zapisy, terminy, konta |
| Serwer poczty uczelni | system zewnętrzny | Dostarcza e-maile z potwierdzeniami i powiadomieniami (OG-02). | adres e-mail studenta |

## Poza zakresem (OUT)

MS Teams, Zoom i USOS nie są częścią systemu.
