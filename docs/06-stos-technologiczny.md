# 6. Stos technologiczny

| Obszar | Technologia | Uzasadnienie |
|---|---|---|
| **Frontend** | React 18 + TypeScript, Vite | Najpopularniejsza biblioteka SPA, duży ekosystem komponentów (kalendarze, formularze). TypeScript wykrywa błędy na etapie kompilacji, co ma znaczenie przy danych medycznych. Vite – szybki build i hot reload. |
| **UI** | Material UI (MUI) | Gotowe, dostępne (WCAG) komponenty – spełnienie NFR-11 bez pisania wszystkiego od zera. |
| **Backend** | Java 21 + Spring Boot 3 | Dojrzały framework do systemów biznesowych; Spring Security (RBAC, JWT), Spring Data JPA, wbudowany scheduler do przypomnień. Silne typowanie i długie wsparcie LTS. |
| **Bezpieczeństwo** | Spring Security, JWT, TOTP (2FA), bcrypt | Standardowe, sprawdzone mechanizmy spełniające NFR-01–NFR-04. |
| **Baza danych** | PostgreSQL 16 | Relacyjna baza z transakcjami ACID – kluczowe przy rezerwacji terminów (brak podwójnych rezerwacji). Darmowa, wydajna, obsługuje JSONB i ograniczenia wykluczające (np. nakładające się sloty). |
| **Migracje bazy** | Flyway | Wersjonowanie schematu bazy razem z kodem. |
| **Dokumentacja API** | OpenAPI 3 (springdoc) + Swagger UI | Automatycznie generowany kontrakt API między frontendem a backendem. |
| **Integracja P1** | Adapter (HL7 FHIR / SOAP), środowisko testowe CSIOZ | Wymagane prawnie do e-recept; adapter izoluje resztę systemu od zmian po stronie P1. |
| **Powiadomienia** | SMSAPI (REST), SMTP | Polski dostawca SMS z prostym API; e-mail jako kanał zapasowy. |
| **Reverse proxy** | Nginx | Wydajny serwer HTTPS, serwowanie SPA, rate limiting. |
| **Konteneryzacja** | Docker + Docker Compose | Identyczne środowisko u każdego członka zespołu i na serwerze; uruchomienie całości jednym poleceniem. |
| **CI/CD** | GitHub Actions | Zintegrowane z repozytorium; testy i build przy każdym PR (NFR-14). |
| **Testy** | JUnit 5, Mockito, Testcontainers; Vitest + React Testing Library; Playwright (E2E) | Testy jednostkowe, integracyjne na prawdziwej bazie w kontenerze i testy end-to-end kluczowych ścieżek (UC-03, UC-11). |
| **Monitoring** | Spring Boot Actuator + Uptime Kuma | Kontrola dostępności (NFR-09) i stanu aplikacji. |
| **Hosting** | VPS w UE (np. OVH / Hetzner) | Dane w EOG zgodnie z RODO (NFR-06), niski koszt. |
| **Narzędzia zespołu** | GitHub (repo, PR, Issues, Projects), diagrams.net | Przegląd kodu przez PR, śledzenie zadań; diagramy w formacie źródłowym `.drawio`. |
