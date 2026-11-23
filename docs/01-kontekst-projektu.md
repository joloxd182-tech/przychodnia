# 1. Kontekst projektu

## 1.1 Opis problemu

Mała/średnia przychodnia POZ i specjalistyczna (ok. 10–15 lekarzy, 3–4 rejestratorki, kilka tysięcy pacjentów) prowadzi zapisy głównie telefonicznie i w papierowym zeszycie lub arkuszu kalkulacyjnym. Skutki:

- długie oczekiwanie na połączenie z rejestracją w godzinach porannych,
- pacjenci nie zgłaszają się na wizyty (*no-show*), a zwolnione terminy przepadają,
- brak jednego miejsca z historią wizyt i dokumentacją medyczną,
- ręczne przepisywanie danych przy wystawianiu e-recept i e-skierowań.

## 1.2 Wizja systemu

**System obsługi przychodni** to aplikacja webowa, która pozwala pacjentom samodzielnie umawiać wizyty przez internet, a personelowi – zarządzać grafikiem, kartoteką pacjentów i elektroniczną dokumentacją medyczną (EDM). System wysyła automatyczne przypomnienia o wizytach, prowadzi listę oczekujących na zwolnione terminy i integruje się z państwowym systemem **P1 (e-zdrowie)** przy wystawianiu e-recept i e-skierowań.

> *Dla pacjentów i personelu przychodni, którzy tracą czas na telefoniczne zapisy i papierową dokumentację, System obsługi przychodni jest aplikacją webową, która umożliwia rezerwację wizyty w mniej niż 2 minuty i prowadzi całą obsługę pacjenta w jednym miejscu – w odróżnieniu od zapisów telefonicznych i arkuszy kalkulacyjnych.*

## 1.3 Cele biznesowe

| ID | Cel | Miernik |
|---|---|---|
| CB-1 | Odciążenie rejestracji | ≥ 50% wizyt umawianych online po 6 miesiącach |
| CB-2 | Mniej nieodbytych wizyt | spadek no-show o 30% dzięki przypomnieniom i liście oczekujących |
| CB-3 | Pełna elektroniczna dokumentacja | 100% wizyt z wpisem w EDM |
| CB-4 | Zgodność z przepisami | zgodność z RODO i ustawą o prawach pacjenta |

## 1.4 Zakres

**W zakresie (MVP):** konta pacjentów, rezerwacja/odwołanie wizyt, grafik lekarzy, lista oczekujących, powiadomienia SMS/e-mail, kartoteka pacjenta, dokumentacja wizyty, e-recepta i e-skierowanie przez P1, panel administratora, log audytowy.

**Poza zakresem:** rozliczenia z NFZ, płatności online, telemedycyna (wideo), aplikacja mobilna natywna, moduł laboratorium.

## 1.5 Aktorzy

| Aktor | Typ | Opis i główne potrzeby |
|---|---|---|
| **Pacjent** | osoba (główny) | Umawia, odwołuje i przekłada wizyty online, otrzymuje przypomnienia, przegląda historię wizyt, zalecenia i kody e-recept. |
| **Rejestratorka** | osoba (główny) | Obsługuje pacjentów telefonicznie i w okienku: zakłada kartotekę, umawia wizyty w imieniu pacjenta, potwierdza przybycie, oznacza nieobecności. |
| **Lekarz** | osoba (główny) | Przegląda swój grafik, przeprowadza wizytę, uzupełnia dokumentację medyczną, wystawia e-recepty i e-skierowania. |
| **Administrator** | osoba (wspierający) | Zarządza kontami personelu i uprawnieniami, definiuje grafik pracy lekarzy, gabinety i specjalizacje. |
| **System P1 (e-zdrowie)** | system zewnętrzny | Państwowa platforma CSIOZ – rejestruje e-recepty i e-skierowania, zwraca kody dostępu. |
| **Bramka SMS / serwer e-mail** | system zewnętrzny | Dostarcza potwierdzenia, przypomnienia i kody e-recept do pacjentów. |
| **Harmonogram (czas)** | aktor czasowy | Wyzwala wysyłkę przypomnień 24 h przed wizytą i nocne kopie zapasowe. |

## 1.6 Słownik pojęć

| Pojęcie | Znaczenie |
|---|---|
| **Wizyta** | zarezerwowany termin u konkretnego lekarza, ma status: zaplanowana / odbyta / odwołana / nieodbyta (no-show) |
| **Slot / termin** | jednostka czasu w grafiku lekarza (domyślnie 15 min) |
| **Grafik** | godziny pracy lekarza w danym gabinecie, podzielone na sloty |
| **Lista oczekujących** | kolejka pacjentów powiadamianych, gdy zwolni się termin u wybranego lekarza |
| **EDM** | elektroniczna dokumentacja medyczna – wywiad, badanie, rozpoznanie (ICD-10), zalecenia |
| **P1** | Platforma e-zdrowia (e-recepta, e-skierowanie, IKP) |
| **No-show** | niestawienie się pacjenta na wizytę bez odwołania |
