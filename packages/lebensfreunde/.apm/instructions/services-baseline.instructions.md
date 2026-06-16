---
description: Lebensfreunde Services — gemeinsame Regeln für alle Microservices.
applyTo: "services/**"
---

# Services — Baseline (alle Microservices)

> Dummy-Scaffold — gilt für jeden Service unter `services/*`. Service-spezifische Dateien überschreiben diese Regeln.

- Jeder Service besitzt seine eigene Datenbank/Schema — kein geteilter DB-Zugriff zwischen Services.
- Inter-Service-Kommunikation bevorzugt event-getrieben (Messaging); synchrone Calls nur mit Timeout, Retry und Circuit-Breaker.
- Idempotenz bei Konsumenten sicherstellen (Events können mehrfach ankommen).
- Health-/Readiness-Endpunkte und strukturiertes Logging mit Korrelations-ID sind Pflicht.
- Konfiguration ausschließlich über Umgebungsvariablen/Secrets, nicht im Code.
- Contracts (API/Events) versioniert; Schemas zentral dokumentiert.
- Jeder Service ist eigenständig deploy- und testbar (kein versteckter Laufzeit-Coupling).
