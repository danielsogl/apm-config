---
description: Lebensfreunde Notifications-Service — Beispiel-Service (E-Mail/Push/SMS-Versand).
applyTo: "services/notifications/**"
---

# Service: Notifications (Beispiel)

> Dummy-Scaffold — exemplarischer konkreter Service. Ergänzt services-baseline.

- Versand-Kanäle (E-Mail, Push, SMS) hinter einem gemeinsamen Channel-Interface.
- Templates versioniert und lokalisiert (i18n) verwalten, nicht inline im Code.
- Zustellung idempotent: pro (User, Event, Kanal) höchstens einmal senden.
- Fehlversuche mit exponentiellem Backoff retrien; endgültig fehlgeschlagene in Dead-Letter-Queue.
- Opt-out/Consent des Nutzers vor jedem Versand prüfen.
- Provider-Keys ausschließlich aus dem Secret-Store.
