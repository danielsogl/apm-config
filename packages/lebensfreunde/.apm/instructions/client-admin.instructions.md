---
description: Lebensfreunde Admin-Client — internes Verwaltungs-Frontend (Angular).
applyTo: "apps/admin/**"
---

# Client: Admin (intern)

> Dummy-Scaffold — an reale App anpassen.

- Zugriff ist rollenbasiert; jede Route durch Auth- und Role-Guards schützen.
- Datenintensive Tabellen mit Virtual Scrolling und serverseitiger Pagination.
- Destruktive Aktionen (Löschen, Sperren) immer mit Bestätigungsdialog und Audit-Log.
- UI aus `libs/ui`; Admin-spezifische Komponenten in `libs/ui-admin` kapseln.
- Formulare als typed Reactive Forms; Validierung clientseitig UND serverseitig.
- Keine produktiven Nutzerdaten in Logs oder Fehlermeldungen ausgeben.
