# Rejestr ryzyk

P = prawdopodobieństwo (1–3), S = skutek (1–3). Ocena 6–9: działamy teraz.

| ID | Rodzaj | Ryzyko | Przyczyna | P×S | Reakcja | Właściciel | Status |
|---|---|---|---|---|---|---|---|
| R-01 | projektowe | Nieobecność członka zespołu | zespół ma 2 osoby | 2×3=6 | ograniczanie: dokumentacja w repo, wzajemne recenzje | Vladyslav | otwarte |
| R-02 | projektowe | Brak odpowiedzi klienta na pytania z Issues #1–#4 | klient odpowiada zgodnie z kartą, po terminie | 2×3=6 | ograniczanie: oznaczone założenia, przypomnienie prowadzącemu | Vitalii | otwarte |
| R-03 | projektowe | Zbyt duży zakres względem czasu | wiele FR i procesów w jednym semestrze | 2×2=4 | ograniczanie: MoSCoW, Won't (now) | Vitalii | otwarte |
| R-04 | produktowe | Serwer poczty uczelni niedostępny lub odrzuca wiadomości | zależność od usługi uczelni, brak reguły (Q-08) | 2×3=6 | ograniczanie: kolejka powiadomień z ponowieniem | Vladyslav | otwarte |
| R-05 | produktowe | Wyciek haseł lub danych studentów | własne konta, numer indeksu to dana osobowa | 2×3=6 | ograniczanie: haszowanie haseł, minimalny zakres danych (NFR-05) | Vitalii | otwarte |
| R-06 | produktowe | Niepotwierdzone reguły biznesowe (limit miejsc, odwołanie konsultacji) | otwarte Issues #2, #3 | 3×2=6 | ograniczanie: parametry konfigurowalne, wczesne pytanie do klienta | Vitalii | otwarte |
