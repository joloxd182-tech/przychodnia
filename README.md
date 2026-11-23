# Przychodnia – system obsługi przychodni

Projekt zespołowy z przedmiotu *Projekt* (etap 1: modelowanie procesów, wymagania funkcjonalne i niefunkcjonalne).

## Zespół (grupa 7)

| Osoba | Rola w etapie 1 |
|---|---|
| Adrian Mrózek | lider zespołu, kontekst projektu, stos technologiczny, konfiguracja repozytorium |
| Kamil Rozmus | model procesu biznesowego, architektura systemu |
| Wiktor Jagosz | wymagania funkcjonalne i niefunkcjonalne, przypadki użycia |

## Dokumentacja (`docs/`)

| Nr | Dokument | Zawartość |
|---|---|---|
| a | [01-kontekst-projektu.md](docs/01-kontekst-projektu.md) | wizja systemu, zakres, lista aktorów |
| b | [02-model-procesu.md](docs/02-model-procesu.md) | diagram aktywności UML z torami (proces obsługi wizyty) |
| c | [03-wymagania.md](docs/03-wymagania.md) | user stories + kryteria akceptacji + MoSCoW, wymagania niefunkcjonalne |
| d | [04-przypadki-uzycia.md](docs/04-przypadki-uzycia.md) | diagram przypadków użycia + opis 2 kluczowych przypadków |
| e | [05-architektura.md](docs/05-architektura.md) | diagram architektury (C4 – kontenery) |
| f | [06-stos-technologiczny.md](docs/06-stos-technologiczny.md) | technologie z uzasadnieniem |

Diagramy znajdują się w `docs/diagramy/` – każdy jako **plik źródłowy** (`.drawio`, otwierany w [diagrams.net](https://app.diagrams.net)) oraz **PNG**.

## Zasady pracy w repozytorium

- Gałąź `main` jest chroniona – zmiany wyłącznie przez **Pull Request** z akceptacją co najmniej jednej innej osoby z zespołu.
- Nazwy gałęzi: `docs/<temat>`, np. `docs/wymagania`.
- Każdy PR opisuje, co zmienia, i wskazuje recenzenta.
