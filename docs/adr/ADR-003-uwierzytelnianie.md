# ADR-003: Własne konta zamiast SSO

**Status:** zaproponowany

**Kontekst:** karta projektu zakłada własną autentykację, a SSO nie jest w zakresie. Klient nie odpowiedział jeszcze, jak student się loguje (Q-07).

**Opcje:**
1. własne konta zakładane przez administratora
2. SSO uczelni
3. dostawca tożsamości w chmurze

**Decyzja:** własne konta (zgodnie z kartą projektu), do potwierdzenia po odpowiedzi klienta na Q-07.

**Konsekwencje:**
- (+) brak zależności od systemów uczelni
- (−) system przechowuje hasła, wymaga bezpiecznego haszowania (R-05)
- (−) trzeba zbudować reset hasła i zarządzanie kontami (FR-14)
