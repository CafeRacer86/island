# Projektkontext: Island Rundreise

Dieses Repository enthält die KI-gestützte Reiseplanung für eine 21-nächtige Island-Rundreise (siehe `README.md` für den Gesamtüberblick, `stuetzpunkte/` für Detailplanungen je Stützpunkt).

## Recherche-Anweisung

Bei Aufgaben in diesem Projekt (POI-Beschreibungen, Öffnungszeiten, Straßenzustände, Buchungsvoraussetzungen, aktuelle Hinweise etc.) aktiv **WebSearch** und **WebFetch** nutzen, statt sich ausschließlich auf Trainingswissen zu verlassen:

* **WebSearch**: für aktuelle Fakten (z.B. Öffnungszeiten von Bädern, Sperrungen von F-Straßen, Preise, saisonale Änderungen) und um POI-Beschreibungen gegenzuprüfen statt zu raten.
* **WebFetch**: um konkrete Quellen (z.B. Vedur.is, Umferdin.is, Road.is, offizielle Parkplatz-/Buchungsseiten) direkt auszuwerten.

Informationen, die nicht recherchiert, sondern aus allgemeinem Wissen ergänzt wurden, im jeweiligen Dokument kurz kennzeichnen (siehe z.B. Hinweis zu den HIGHLIGHTS_PINS im README), damit unverifizierte Angaben erkennbar bleiben.

## Google Maps MCP-Server

Lokal (nicht im Repo, da API-Key-basiert) ist ein Google-Maps-MCP-Server konfiguriert (`google-maps`, Paket `@cablate/mcp-google-map`), der Geocoding, Places-Details, Distanzmatrizen und Routen-/Wegpunkt-Optimierung bereitstellt. Nutzen für:
* Verifizierung von POI-Koordinaten und -Details statt Trainingswissen/Suchlinks.
* Prüfung, ob eine Tagesroute mit mehreren POIs zeitlich/fahrtechnisch plausibel ist (Distanzmatrix).
* Berechnung optimierter Tagesrouten (bis 25 Wegpunkte) bei der Detailplanung je Stützpunkt.

Der API-Key liegt ausschließlich in der lokalen, nicht versionierten `.claude/settings.local.json` — niemals in eine committete Datei übernehmen.
