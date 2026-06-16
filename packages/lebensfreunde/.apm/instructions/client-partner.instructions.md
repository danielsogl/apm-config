---
description: Lebensfreunde Partner-Client — Frontend für externe Partner/B2B (Angular).
applyTo: "apps/partner/**"
---

# Client: Partner (B2B)

> Dummy-Scaffold — an reale App anpassen.

- Mandantenfähigkeit (Multi-Tenancy): Tenant-Kontext aus dem Auth-Token, nie aus der URL vertrauen.
- Jede Anzeige strikt auf den Tenant des eingeloggten Partners filtern.
- White-Labeling über Theme-Tokens aus `libs/ui`, keine hartkodierten Farben/Logos.
- Exporte (CSV/PDF) serverseitig generieren, nicht im Client zusammenbauen.
- Rate-Limits und Kontingente der Partner-APIs im UI sichtbar machen.
- API-Zugriff nur über `libs/data-access` mit Tenant-Scoped-Clients.
