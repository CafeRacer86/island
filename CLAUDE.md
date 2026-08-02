# Projektkontext: Island Rundreise

Dieses Repository enthält die KI-gestützte Reiseplanung für eine 21-nächtige Island-Rundreise (siehe `README.md` für den Gesamtüberblick, `stuetzpunkte/` für Detailplanungen je Stützpunkt).

## Recherche-Anweisung

Bei Aufgaben in diesem Projekt (POI-Beschreibungen, Öffnungszeiten, Straßenzustände, Buchungsvoraussetzungen, aktuelle Hinweise etc.) aktiv **WebSearch** und **WebFetch** nutzen, statt sich ausschließlich auf Trainingswissen zu verlassen:

* **WebSearch**: für aktuelle Fakten (z.B. Öffnungszeiten von Bädern, Sperrungen von F-Straßen, Preise, saisonale Änderungen) und um POI-Beschreibungen gegenzuprüfen statt zu raten.
* **WebFetch**: um konkrete Quellen (z.B. Vedur.is, Umferdin.is, Road.is, offizielle Parkplatz-/Buchungsseiten) direkt auszuwerten.

Informationen, die nicht recherchiert, sondern aus allgemeinem Wissen ergänzt wurden, im jeweiligen Dokument kurz kennzeichnen (siehe z.B. Hinweis zu den HIGHLIGHTS_PINS im README), damit unverifizierte Angaben erkennbar bleiben.
