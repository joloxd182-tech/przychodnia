# Wymagania

## Wymagania funkcjonalne

Priorytety ustaliliśmy metodą MoSCoW:
- M - must have
- S - should have
- C - could have
- W - won't have (nie w tej wersji)

### Pacjent

**US1. Rejestracja konta (M)**
Jako pacjent chcę założyć konto, żeby móc sam umawiać wizyty.

Kryteria akceptacji:
- pacjent podaje imię, nazwisko, PESEL, e-mail, telefon i hasło
- po rejestracji dostaje maila z linkiem aktywacyjnym
- jeśli PESEL jest niepoprawny, konto nie zostaje założone i pojawia się komunikat
- nie można założyć drugiego konta na ten sam PESEL lub e-mail

**US2. Umówienie wizyty (M)**
Jako pacjent chcę wybrać lekarza i wolny termin, żeby umówić się bez dzwonienia.

Kryteria akceptacji:
- po wybraniu specjalizacji widać lekarzy i ich wolne terminy na 30 dni do przodu
- po potwierdzeniu wizyta jest zapisana, a pacjent dostaje SMS i maila
- dwie osoby nie mogą zarezerwować tego samego terminu
- można mieć tylko jedną zaplanowaną wizytę u danego lekarza

**US3. Odwołanie lub przełożenie wizyty (M)**
Jako pacjent chcę odwołać albo przełożyć wizytę, kiedy nie mogę przyjść.

Kryteria akceptacji:
- wizytę można odwołać online najpóźniej 2 godziny przed terminem
- odwołany termin znowu jest wolny
- przy przekładaniu stary termin zwalnia się dopiero po zarezerwowaniu nowego

**US4. Przypomnienie o wizycie (M)**
Jako pacjent chcę dostać przypomnienie dzień przed wizytą, żeby o niej nie zapomnieć.

Kryteria akceptacji:
- SMS przychodzi 24 godziny przed wizytą
- w SMS-ie jest data, godzina, lekarz, gabinet i link do odwołania wizyty
- dla odwołanych wizyt przypomnienie nie jest wysyłane

**US5. Lista oczekujących (S)**
Jako pacjent chcę zapisać się na listę oczekujących, żeby dostać wcześniejszy termin, jeśli ktoś zrezygnuje.

Kryteria akceptacji:
- opcja pojawia się, gdy u lekarza nie ma wolnych terminów w ciągu 14 dni
- kiedy zwolni się termin, pierwsza osoba z listy dostaje powiadomienie i ma 30 minut na potwierdzenie
- jak nie potwierdzi, termin dostaje następna osoba

**US6. Historia wizyt (S)**
Jako pacjent chcę widzieć swoje poprzednie wizyty, zalecenia i kody recept.

Kryteria akceptacji:
- lista wizyt jest posortowana od najnowszej
- przy odbytej wizycie widać zalecenia i kody e-recept
- pacjent nie widzi notatek, które lekarz oznaczył jako wewnętrzne

### Rejestratorka

**US7. Kartoteka pacjenta (M)**
Jako rejestratorka chcę założyć kartotekę pacjentowi, który nie ma konta, żeby móc go zapisać na wizytę.

Kryteria akceptacji:
- po wpisaniu PESEL system sprawdza, czy pacjent już jest w bazie
- wymagane są imię, nazwisko, PESEL i telefon

**US8. Zapisanie pacjenta na wizytę (M)**
Jako rejestratorka chcę zapisać pacjenta na wizytę, kiedy dzwoni albo przychodzi do okienka.

Kryteria akceptacji:
- widać grafik wszystkich lekarzy w widoku dnia i tygodnia
- po zapisaniu pacjent dostaje SMS z potwierdzeniem

**US9. Potwierdzenie przyjścia pacjenta (M)**
Jako rejestratorka chcę zaznaczyć, czy pacjent przyszedł, żeby lekarz wiedział, kto czeka.

Kryteria akceptacji:
- po zaznaczeniu "przyszedł" pacjent pojawia się na liście u lekarza
- można zaznaczyć "nie przyszedł" po 15 minutach od godziny wizyty
- pacjent, który 3 razy w ciągu pół roku nie przyszedł, może się umawiać tylko przez rejestrację

### Lekarz

**US10. Grafik na dzień (M)**
Jako lekarz chcę widzieć listę pacjentów na dziś, żeby wiedzieć, kto jest następny.

**US11. Dokumentacja wizyty (M)**
Jako lekarz chcę zapisać wywiad, badanie, rozpoznanie i zalecenia, żeby dokumentacja była w systemie.

Kryteria akceptacji:
- przy rozpoznaniu system podpowiada kody ICD-10
- po zamknięciu wizyty nie można zmienić wpisu, można tylko dodać uzupełnienie
- wpis zapisuje się automatycznie co 30 sekund

**US12. E-recepta (M)**
Jako lekarz chcę wystawić e-receptę, żeby pacjent dostał kod na telefon.

Kryteria akceptacji:
- recepta jest wysyłana do P1, a kod pojawia się na ekranie
- jeśli P1 nie odpowiada, lekarz dostaje komunikat, a system ponawia wysyłanie co 5 minut

**US13. E-skierowanie (S)**
Jako lekarz chcę wystawić e-skierowanie do specjalisty albo na badania.

**US14. Historia leczenia (S)**
Jako lekarz chcę zobaczyć poprzednie wizyty i rozpoznania pacjenta.

### Administrator

**US15. Grafik lekarzy (M)**
Jako administrator chcę ustawiać godziny pracy lekarzy, żeby system wiedział, jakie terminy są dostępne.

Kryteria akceptacji:
- można ustawić stały grafik, np. poniedziałki i środy 8-14
- można dodać urlop, a system pokazuje wizyty, które trzeba odwołać

**US16. Konta pracowników (M)**
Jako administrator chcę zakładać konta pracownikom i nadawać im role.

**US17. Raport wizyt (C)**
Jako administrator chcę zobaczyć, ile było wizyt i nieobecności w danym miesiącu.

**US18. Płatności online (W)**
Jako pacjent chcę zapłacić online za wizytę prywatną. Nie robimy tego w pierwszej wersji.

**US19. Teleporady (W)**
Jako pacjent chcę mieć wizytę przez wideo. Nie robimy tego w pierwszej wersji.

## Wymagania niefunkcjonalne

1. Bezpieczeństwo - połączenie tylko przez HTTPS.
2. Bezpieczeństwo - hasła są przechowywane jako hash (bcrypt), minimum 10 znaków.
3. Bezpieczeństwo - pracownicy logują się z weryfikacją dwuetapową.
4. Bezpieczeństwo - każdy użytkownik ma dostęp tylko do danych zgodnych z jego rolą, pacjent widzi tylko swoje dane.
5. RODO - zapisujemy, kto i kiedy przeglądał lub zmieniał dane medyczne.
6. RODO - dane są przechowywane na serwerze w UE.
7. Wydajność - odpowiedź systemu w czasie poniżej 0,5 sekundy przy 200 użytkownikach naraz.
8. Wydajność - wyszukanie wolnych terminów zajmuje mniej niż sekundę.
9. Dostępność - system działa co najmniej 99,5% czasu w godzinach pracy przychodni.
10. Kopie zapasowe - baza jest kopiowana codziennie, kopie są trzymane 30 dni.
11. Użyteczność - strona działa na telefonie i komputerze.
12. Użyteczność - umówienie wizyty zajmuje nowemu użytkownikowi maksymalnie 2 minuty.
13. Dostępność dla osób z niepełnosprawnościami - zgodność ze standardem WCAG 2.1 AA.
14. Kompatybilność - system działa w aktualnych wersjach Chrome, Firefox, Edge i Safari.
15. Utrzymanie - testy jednostkowe pokrywają co najmniej 70% kodu backendu.
16. Język - interfejs po polsku, daty w formacie DD.MM.RRRR.
