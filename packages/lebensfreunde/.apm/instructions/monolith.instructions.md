---
description: Lebensfreunde Monolith — zentrales Backend mit der Kerndomäne.
applyTo: "apps/monolith/**"
---

# Monolith (Kern-Backend)

> Dummy-Scaffold — an reales Backend anpassen.

- Layering einhalten: Controller/API → Application/Use-Case → Domain → Infrastructure. Keine Abkürzungen über Layer hinweg.
- Domänenlogik gehört in die Domain-Schicht, nicht in Controller oder Repositories.
- Datenbankzugriff nur über Repositories; Migrations sind versioniert und vorwärtskompatibel.
- Öffentliche REST/Contract-Endpunkte sind versioniert; Breaking Changes nur über neue Version.
- Kommunikation zu Services bevorzugt asynchron über Events/Messaging; synchrone Calls nur wenn nötig.
- Transaktionsgrenzen explizit setzen; keine langlaufenden Transaktionen über externe Calls.
- Strukturierte Logs mit Korrelations-ID; keine personenbezogenen Daten im Klartext loggen.
- Jede Use-Case-Logik durch Unit-Tests, jeder Endpoint durch Integrationstests abgedeckt.
