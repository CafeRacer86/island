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
