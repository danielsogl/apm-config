---
description: Lebensfreunde — projektweite Engineering-Regeln (Monorepo-Baseline). Ergänzt die STRÖER-Baseline.
applyTo: "**"
---

# Lebensfreunde — Projekt-Baseline

> Dummy-Scaffold. Regeln vor dem ersten echten Einsatz prüfen und an das reale Repo-Layout anpassen.

## Architektur-Überblick

Das Lebensfreunde-Monorepo besteht aus:

- **4 Clients** (`apps/web`, `apps/admin`, `apps/mobile`, `apps/partner`) — Angular-Frontends.
- **1 Monolith** (`apps/monolith`) — zentrales Backend, hält die Kerndomäne.
- **n Services** (`services/*`) — fachlich geschnittene Microservices.
- **n Angular Shared Libs** (`libs/*`) — wiederverwendbare UI-, Data-Access- und Util-Bibliotheken.

Spezifischere Regeln je Baustein liegen in den jeweiligen `*.instructions.md` und überschreiben diese Baseline bei Konflikten (engerer `applyTo`-Scope gewinnt).

## Allgemeine Regeln

- Code, Kommentare, Commit-Messages und PR-Titel auf Englisch.
- Conventional Commits verwenden (`feat:`, `fix:`, `chore:`, `refactor:` …).
- Keine Secrets, Tokens oder Zugangsdaten ins Repo committen — `.env`-Werte über das Secret-Management beziehen.
- Public APIs zwischen Clients, Monolith und Services sind Verträge: Breaking Changes nur versioniert und abgestimmt.
- Shared Code gehört in `libs/*`, nicht per Copy-Paste in mehrere Apps.
- Jede neue Funktionalität wird durch Tests abgesichert; bestehende Tests bleiben grün.

## Tooling

- Paketmanager und Task-Runner laut Root-Konfiguration verwenden (nicht mischen).
- Vor dem Commit: Lint + Format + betroffene Tests lokal laufen lassen.
