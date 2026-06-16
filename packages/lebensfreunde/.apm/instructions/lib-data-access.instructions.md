---
description: Lebensfreunde libs/data-access — geteilte API-/State-Zugriffsschicht (Angular).
applyTo: "libs/data-access/**"
---

# Lib: Data-Access (Beispiel)

> Dummy-Scaffold — exemplarische konkrete Lib. Ergänzt angular-libs.

- Einziger Ort für `HttpClient`-Zugriffe; Apps und UI-Libs greifen nie direkt auf HTTP zu.
- Server-State über die `resource()`-API bzw. Signal-Stores; klare Trennung Server- vs. Client-State.
- DTOs an der Grenze auf Domänen-Modelle mappen; rohe API-Shapes nicht nach außen leaken.
- Fehler typisiert behandeln und an die UI weiterreichen — kein stilles Verschlucken.
- Auth-/Tenant-Header zentral über Interceptors setzen, nicht pro Call.
- Endpunkt-URLs/Config über Injection-Tokens, nicht hartkodiert.
