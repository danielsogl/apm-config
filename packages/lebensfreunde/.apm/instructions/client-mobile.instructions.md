---
description: Lebensfreunde Mobile-Client — App-Frontend (Angular + Capacitor/Ionic).
applyTo: "apps/mobile/**"
---

# Client: Mobile

> Dummy-Scaffold — an reale App anpassen.

- Native Funktionen ausschließlich über Capacitor-Plugins kapseln, nicht direkt aufrufen.
- Offline-First denken: Daten lokal cachen, Sync-Konflikte explizit auflösen.
- Touch-Targets ≥ 44px, sichere Bereiche (Safe Area Insets) respektieren.
- Bilder und Assets für mobile Netze optimieren; Lazy Loading konsequent.
- Platform-Checks (`iOS`/`Android`) über die zentrale Platform-Service-Abstraktion.
- Push-Notifications und Permissions defensiv behandeln (User kann ablehnen).
