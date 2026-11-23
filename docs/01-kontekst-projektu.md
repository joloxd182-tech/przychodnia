# Kontekst projektu

## Opis

Tematem projektu jest system dla przychodni. Zakładamy, że to średniej wielkości przychodnia, w której pracuje kilkunastu lekarzy różnych specjalizacji i kilka rejestratorek.

Obecnie pacjenci zapisują się głównie przez telefon. Rano ciężko się dodzwonić, a zapisy są prowadzone w arkuszu albo zeszycie. Część pacjentów nie przychodzi na wizyty i nikt ich wcześniej nie odwołuje, więc terminy przepadają. Dokumentacja z wizyt też nie jest w jednym miejscu.

## Wizja systemu

Chcemy zrobić aplikację webową, w której pacjent może sam umówić się do lekarza przez internet, odwołać wizytę albo ją przełożyć. Przed wizytą dostaje SMS z przypomnieniem. Jeśli nie ma wolnych terminów, może zapisać się na listę oczekujących i dostanie powiadomienie, kiedy ktoś zwolni termin.

Personel przychodni ma swój panel. Rejestratorka widzi grafik wszystkich lekarzy i może zapisywać pacjentów, którzy dzwonią albo przychodzą osobiście. Lekarz widzi swoich pacjentów na dany dzień, uzupełnia dokumentację z wizyty i wystawia e-recepty. E-recepty idą do systemu P1, a pacjent dostaje kod SMS-em.

Celem jest odciążenie rejestracji, zmniejszenie liczby nieodbytych wizyt i trzymanie całej dokumentacji w jednym systemie.

## Zakres

W pierwszej wersji systemu będą:
- konta pacjentów i logowanie
- umawianie, odwoływanie i przekładanie wizyt
- grafik lekarzy
- lista oczekujących
- przypomnienia SMS i e-mail
- kartoteka pacjenta
- dokumentacja z wizyty
- e-recepty i e-skierowania przez P1
- panel administratora

Nie robimy: płatności online, teleporad, rozliczeń z NFZ i aplikacji mobilnej.

## Aktorzy

| Aktor | Opis |
|---|---|
| Pacjent | umawia i odwołuje wizyty przez internet, dostaje przypomnienia, przegląda historię wizyt i kody e-recept |
| Rejestratorka | zapisuje pacjentów przez telefon i w okienku, zakłada kartoteki, potwierdza przyjście pacjenta albo zaznacza, że nie przyszedł |
| Lekarz | sprawdza swój grafik, prowadzi wizytę, uzupełnia dokumentację, wystawia e-recepty i skierowania |
| Administrator | zakłada konta pracownikom, ustawia uprawnienia i grafiki pracy lekarzy |
| System P1 | zewnętrzny system e-zdrowia, rejestruje e-recepty i e-skierowania |
| Bramka SMS / poczta | zewnętrzne usługi do wysyłania SMS-ów i maili |

## Słownik

- Wizyta - zarezerwowany termin u lekarza. Może być zaplanowana, odbyta, odwołana albo nieodbyta.
- Slot - jeden termin w grafiku lekarza, domyślnie 15 minut.
- Lista oczekujących - kolejka pacjentów, którzy chcą dostać wcześniejszy termin.
- EDM - elektroniczna dokumentacja medyczna.
- No-show - pacjent nie przyszedł na wizytę i jej nie odwołał.
