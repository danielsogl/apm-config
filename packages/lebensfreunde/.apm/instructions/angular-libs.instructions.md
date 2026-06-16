---
description: Lebensfreunde Angular Shared Libs — gemeinsame Regeln für alle Bibliotheken unter libs/.
applyTo: "libs/**"
---

# Angular Shared Libs — Baseline

> Dummy-Scaffold — gilt für jede Lib unter `libs/*`. Lib-spezifische Dateien überschreiben diese Regeln.

- Jede Lib hat eine klare Verantwortung und einen schmalen Public-API-`index.ts` (Barrel); nichts darüber hinaus exportieren.
- Keine App→App- oder Lib→App-Importe; Abhängigkeiten zeigen nur von Apps nach Libs und entlang der Lib-Typ-Grenzen.
- Lib-Typen trennen: `feature`, `ui`, `data-access`, `util` — `util`/`ui` dürfen keine `data-access`-Abhängigkeiten ziehen.
- Nur Standalone-APIs (Components/Directives/Pipes), Signals und `inject()`; keine NgModules für neuen Code.
- Components `OnPush` (bzw. Signal-basiert) und ohne direkte HTTP-/Router-Seiteneffekte halten.
- Public API ist ein Vertrag — Breaking Changes versionieren und dokumentieren.
- Jede Lib bringt eigene Unit-Tests mit und ist isoliert testbar.
