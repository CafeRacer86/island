# Projektkontext: Island Rundreise

Dieses Repository enthält die KI-gestützte Reiseplanung für eine 21-nächtige Island-Rundreise (siehe `README.md` für den Gesamtüberblick, `stuetzpunkte/` für Detailplanungen je Stützpunkt).

## Recherche-Anweisung

Bei Aufgaben in diesem Projekt (POI-Beschreibungen, Öffnungszeiten, Straßenzustände, Buchungsvoraussetzungen, aktuelle Hinweise etc.) aktiv **WebSearch** und **WebFetch** nutzen, statt sich ausschließlich auf Trainingswissen zu verlassen:

* **WebSearch**: für aktuelle Fakten (z.B. Öffnungszeiten von Bädern, Sperrungen von F-Straßen, Preise, saisonale Änderungen) und um POI-Beschreibungen gegenzuprüfen statt zu raten.
* **WebFetch**: um konkrete Quellen (z.B. Vedur.is, Umferdin.is, Road.is, offizielle Parkplatz-/Buchungsseiten) direkt auszuwerten.

Informationen, die nicht recherchiert, sondern aus allgemeinem Wissen ergänzt wurden, im jeweiligen Dokument kurz kennzeichnen (siehe z.B. Hinweis zu den HIGHLIGHTS_PINS im README), damit unverifizierte Angaben erkennbar bleiben.

## Google Maps MCP-Server

Lokal (nicht im Repo, da API-Key-basiert) ist in `.claude/settings.local.json` ein Google-Maps-MCP-Server eingetragen (`google-maps`, Paket `@cablate/mcp-google-map`), gedacht für Geocoding, Places-Details, Distanzmatrizen und Routen-/Wegpunkt-Optimierung. Nutzen für:
* Verifizierung von POI-Koordinaten und -Details statt Trainingswissen/Suchlinks.
* Prüfung, ob eine Tagesroute mit mehreren POIs zeitlich/fahrtechnisch plausibel ist (Distanzmatrix).
* Berechnung optimierter Tagesrouten (bis 25 Wegpunkte) bei der Detailplanung je Stützpunkt.

**Bekannter Stand (2026-08-02):** Der Eintrag unter `mcpServers` in `settings.local.json` wird von Claude Code nicht automatisch als MCP-Server geladen (`claude mcp list` zeigt ihn nicht an, keine zugehörigen Tools verfügbar). Um ihn tatsächlich zu verbinden, müsste er korrekt registriert werden, z. B. via `claude mcp add-json google-maps '{"command":"npx","args":["-y","@cablate/mcp-google-map","--stdio"],"env":{"GOOGLE_MAPS_API_KEY":"..."}}'` (oder Projekt-`.mcp.json`), danach neue Session starten.

**Fallback, solange der MCP-Server nicht verbunden ist:** Der API-Key selbst ist gültig und sowohl Geocoding API als auch Places API (New) sind freigeschaltet (verifiziert per direktem REST-Call). Bei Bedarf direkt per Bash/curl abfragen, Key aus `.claude/settings.local.json` (`mcpServers.google-maps.env.GOOGLE_MAPS_API_KEY`):

```bash
# Geocoding
curl -s "https://maps.googleapis.com/maps/api/geocode/json?address=<ORT>&key=<KEY>"

# Places API (New) – Textsuche
curl -s -X POST "https://places.googleapis.com/v1/places:searchText" \
  -H "Content-Type: application/json" \
  -H "X-Goog-Api-Key: <KEY>" \
  -H "X-Goog-FieldMask: places.displayName,places.formattedAddress,places.location" \
  -d '{"textQuery":"<SUCHBEGRIFF>"}'
```

Hinweis: Die CLI des npm-Pakets (`npx @cablate/mcp-google-map exec ...`) hat für manche Tools (z. B. `search_nearby`) einen Bug (`Cannot read properties of undefined (reading 'isCoordinates')`) — im Zweifel den direkten REST-Call bevorzugen.

Der API-Key liegt ausschließlich in der lokalen, nicht versionierten `.claude/settings.local.json` — niemals in eine committete Datei übernehmen, auch nicht in Beispiel-Snippets in anderen Dateien.

## Chrome DevTools MCP-Server (echte Buchungsportal-Prüfungen)

Für echte Verfügbarkeitsprüfungen auf Buchungsportalen (booking.com etc. — `WebFetch`/`WebSearch` liefern dort keinen nutzbaren Inhalt, JS-gerendert) ist lokal per `claude mcp add-json chrome-devtools '{"command":"npx","args":["-y","chrome-devtools-mcp@latest"]}'` ein `chrome-devtools`-MCP-Server registriert (lokale Projekt-Config, nicht im Repo versioniert).

**Bekannter Stand (2026-08-02):** Nach der Registrierung zeigt `claude mcp list` den Server als verbunden (`chrome-devtools: npx -y chrome-devtools-mcp@latest - ✔ Connected`), aber die zugehörigen Tools stehen erst in einer **neu gestarteten Session** zur Verfügung — die laufende Session, in der die Registrierung passiert, lädt sie nicht nach.

Genutzt für Ticket [Buchungsportal-Verfügbarkeitsszenarien Süd-Island](.scratch/island-rundreise/issues/03-buchungsportal-verfuegbarkeitsszenarien.md).

### Booking.com-Suchen mit chrome-devtools: Ablauf & Filter (Stand 2026-08-02, verifiziert)

**Grundablauf pro Suche:**
1. `new_page` (oder `navigate_page`) mit URL `https://www.booking.com/searchresults.html?ss=<ORT>&checkin=<YYYY-MM-DD>&checkout=<YYYY-MM-DD>&group_adults=2&no_rooms=1&group_children=0` (Ort URL-encodiert, z.B. `V%C3%ADk` für „Vík").
2. Cookie-Banner **und** Sign-in-Modal wegklicken (`take_snapshot`, dann auf „Decline“/„Accept" bzw. das X/„Dismiss" des Sign-in-Popups klicken) — sonst blockieren beide nachfolgende Interaktionen teils unsichtbar.
3. Für Pflicht-Filter (eigenes Bad, Küche/Küchenzeile) **nicht** den `nflt`-URL-Parameter raten — die Codes sind nicht dokumentiert und falsch geratene Codes liefern lautlos 0 Treffer (z.B. `hotelfacility=107;facility=2;roomfacility=11` war falsch). Stattdessen einmal über die Filterleiste im UI klicken (Checkboxen „Private bathroom“ und „Kitchen/Kitchenette“ unter „Popular filters“ bzw. „Room facilities“) und danach die resultierende URL auslesen — daraus ergab sich der **verifizierte** Code: `nflt=roomfacility%3D999%3Broomfacility%3D38` (999 = Private bathroom, 38 = Kitchen/Kitchenette). Dieser Parameter kann für weitere Suchen direkt an die Such-URL angehängt werden, ohne erneut über das UI zu gehen.
4. Ergebnisse **nicht** per `take_snapshot` (riesiger a11y-Tree, viel Footer-Rauschen) sondern per `evaluate_script` extrahieren, z.B.:
   ```js
   () => Array.from(document.querySelectorAll('[data-testid="property-card"]')).map(c => ({
     name: c.querySelector('[data-testid="title"]')?.innerText,
     price: c.querySelector('[data-testid="price-and-discounted-price"]')?.innerText,
     desc: c.querySelector('[data-testid="recommended-units"]')?.innerText,
     href: c.querySelector('a')?.href
   }))
   ```
   `desc` enthält u.a. „Kostenlose Stornierung"/„Free cancellation" als Text, wenn vorhanden (sonst fehlt die Zeile). Direktlinks: `href` auf `origin+pathname` kürzen (Tracking-Parameter abschneiden) und eigene `checkin`/`checkout`/`group_adults`-Parameter anhängen, um einen stabilen, teilbaren Link für einen bestimmten Zeitraum zu bekommen.
5. Der Filter-Facet-Bereich zeigt auch ohne Klick die Trefferzahl pro Facette an (z.B. „Kitchen/Kitchenette: 1 property“); fehlt eine Facette komplett in der Liste, gibt es 0 Treffer dafür in der aktuellen (ungefilterten) Ergebnismenge — spart in solchen Fällen einen Klick.
