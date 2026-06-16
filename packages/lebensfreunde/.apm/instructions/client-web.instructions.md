---
description: Lebensfreunde Web-Client — öffentliches Angular-Frontend für Endnutzer.
applyTo: "apps/web/**"
---

# Client: Web (Endnutzer)

> Dummy-Scaffold — an reale App anpassen.

- Standalone Components, Signals und das moderne `inject()`-Pattern verwenden; keine NgModules für neuen Code.
- State über Signals/`signal`-Stores; serverseitige Daten über die `resource()`-API laden.
- Routing lazy; jede Feature-Route als eigener lazy-geladener Chunk.
- UI ausschließlich aus `libs/ui` beziehen — keine eigenen One-off-Komponenten duplizieren.
- API-Zugriff nur über `libs/data-access`, nie direkt `HttpClient` in Components.
- Accessibility: ARIA-Rollen, Fokus-Management und Tastaturbedienung sind Pflicht.
- SSR/Hydration-Kompatibilität beachten (kein direkter `window`/`document`-Zugriff ohne Guard).
