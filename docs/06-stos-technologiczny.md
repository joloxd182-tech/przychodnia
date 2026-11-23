# Stos technologiczny

**Frontend: React + TypeScript**
React jest popularny i jest dużo gotowych komponentów, np. kalendarzy i formularzy. TypeScript pomaga wyłapać błędy wcześniej. Do wyglądu użyjemy biblioteki Material UI.

**Backend: Java + Spring Boot**
Spring Boot dobrze nadaje się do takich systemów. Ma gotowe rozwiązania do logowania i uprawnień (Spring Security), do pracy z bazą (Spring Data JPA) i do zadań uruchamianych o określonej godzinie, czyli np. wysyłania przypomnień.

**Baza danych: PostgreSQL**
Potrzebujemy relacyjnej bazy z transakcjami, żeby dwie osoby nie mogły zarezerwować tego samego terminu. PostgreSQL jest darmowy i sprawdzony. Do zmian w strukturze bazy użyjemy Flyway.

**Nginx**
Jako serwer, który obsługuje HTTPS i przekazuje zapytania do backendu.

**Docker i Docker Compose**
Każdy z nas może uruchomić cały projekt jednym poleceniem i mieć takie samo środowisko. Tak samo uruchomimy to na serwerze.

**GitHub i GitHub Actions**
Repozytorium, pull requesty i zadania mamy na GitHubie. GitHub Actions będzie automatycznie uruchamiać testy przy każdym PR.

**Testy: JUnit, Mockito, Playwright**
JUnit i Mockito do testów backendu, Playwright do testów całej aplikacji w przeglądarce.

**Integracje**
- System P1 do e-recept i e-skierowań (jest środowisko testowe)
- SMSAPI do wysyłania SMS-ów
- serwer SMTP do maili

**Serwer**
VPS w Polsce lub UE, żeby dane były przechowywane zgodnie z RODO.

**Diagramy**
diagrams.net (draw.io), bo jest darmowy i działa w przeglądarce.
