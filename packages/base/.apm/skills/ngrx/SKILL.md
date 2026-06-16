---
name: ngrx
description: STRÖER-Konventionen für State-Management mit NgRx in Angular (klassischer Store und @ngrx/signals Signal Store). Einsetzen beim Entwerfen, Reviewen oder Refactoren von Actions, Reducers, Effects, Selectors oder Signal Stores.
---

# NgRx — STRÖER-Konventionen

State-Management-Leitplanken für Angular-Apps. Gilt für den klassischen Global Store
(`@ngrx/store`, `@ngrx/effects`) und den `@ngrx/signals` Signal Store.

## Wann welcher Store

- **Signal Store (`@ngrx/signals`)** ist die Standardwahl für neue Features — lokaler oder
  feature-naher State, weniger Boilerplate, Signals-nativ.
- **Global Store (`@ngrx/store`)** nur für echten, app-weit geteilten State mit mehreren
  unabhängigen Konsumenten oder komplexen Seiteneffekten.

## Do's

- Actions **event-driven** benennen: `[Source] Event` (z. B. `[Login Page] Submit Clicked`),
  nicht als Befehle.
- State ausschließlich über **Selectors** lesen; Komponenten greifen nie direkt in den State.
- Selectors klein und komponierbar halten; abgeleitete Werte via `createSelector` memoisieren.
- Reducer **pure** halten — keine Seiteneffekte, keine Mutationen (immer neue Referenzen).
- Alle Seiteneffekte in **Effects**; externe Calls mit `switchMap`/`concatMap`/`exhaustMap`
  passend zur Semantik wählen und Fehler im Stream behandeln (`catchError`).
- State-Shape **normalisieren** (z. B. `@ngrx/entity`) statt verschachtelter Arrays.
- Signal Store mit `withState`, `withComputed`, `withMethods` strukturieren; `patchState`
  für Updates verwenden.

## Don'ts

- Keine Geschäftslogik in Komponenten oder Effects — Logik gehört in Reducer/Selectors bzw.
  pure Funktionen.
- Kein direkter `store.select(...).subscribe(...)` mit manuellem State-Halten in Komponenten —
  `toSignal`/`async`-Pipe nutzen.
- Keine "Command"-Actions, die von mehreren Reducern geteilt werden, um Logik zu sparen.
- Reducer nicht für API-Calls oder Navigation missbrauchen.
- Kein nicht-serialisierbarer State (Klassen-Instanzen, Funktionen, Promises) im Store.
- `mergeMap` nicht als Default für Effects — führt zu Race Conditions; bewusst wählen.
