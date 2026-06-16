---
description: Lebensfreunde Matching-Service — Beispiel-Service (Vorschläge/Matching-Logik).
applyTo: "services/matching/**"
---

# Service: Matching (Beispiel)

> Dummy-Scaffold — exemplarischer konkreter Service. Ergänzt services-baseline.

- Matching-Algorithmen hinter einer austauschbaren Strategy-Schnittstelle kapseln.
- Scoring-Parameter konfigurierbar halten, nicht hartkodieren.
- Ergebnisse cachen, wenn Eingaben unverändert; Cache-Invalidierung bei Profiländerung.
- Rechenintensive Jobs asynchron über die Queue, nicht im Request-Pfad.
- Keine personenbezogenen Profildaten über die Service-Grenze hinaus exponieren — nur IDs/Scores.
