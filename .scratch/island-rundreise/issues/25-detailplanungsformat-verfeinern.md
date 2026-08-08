Type: grilling
Status: resolved
Assignee: claude

## Question

Bevor die Detailplanungs-Tickets für die übrigen Stützpunkte (18-24) bearbeitet werden, möchte Ralf das Format anhand von [stuetzpunkte/01_ferjukot.md](../../../stuetzpunkte/01_ferjukot.md) verfeinern und daraus verbindliche Regeln für alle künftigen Detailplanungen ableiten: Google-Maps-Links, eine neue Wanderungen-Recherche-Sektion, eine Besonderheiten-der-Region-Sektion, angepasste Umzugstage (Checkout ~11h/Check-in ~16h) und tagesbezogene Optional-Ziele.

## Comments

Grilling-Session ergab folgende Entscheidungen:

1. **Google-Maps-Links:** Jeder konkrete, physisch aufsuchbare Ort wird verlinkt (auch Supermärkte, Museen, Parkplätze, Trailheads) — keine reinen Straßennamen/Regionsbezeichnungen ohne festen Punkt.
2. **Wanderungen-Sektion (neu, eigener Abschnitt am Ende vor Plan B):** Tabellenformat, zwei Teile:
   - a) Kurztouren an/zu den bereits geplanten POIs (Länge, Höhenmeter, Startpunkt+Link) — auch wenn redundant zur Tagesplanung, da dort nur im Fließtext erwähnt.
   - b) 1-2 separate Top-Empfehlungen für die Region, unabhängig von den geplanten POIs, mit Länge, Höhenmeter, Bewertung, Startpunkt (Maps-Link) und Quelle (Link). Primärquelle: **AllTrails** (Bewertung/Länge/Höhenmeter), ergänzend **Komoot** für Startpunkt-Navigation, wenn AllTrails keine ausreichenden Daten liefert.
   - Direkter WebFetch auf AllTrails-Seiten schlägt fehl (403 Forbidden, Bot-Schutz) — Daten müssen über WebSearch-Snippets extrahiert werden, nicht per direktem Fetch.
3. **Besonderheiten der Region:** Eigene neue Sektion (nicht in Stützpunktspezifische Überlegungen integriert) — geologische/kulturelle/fotografische Alleinstellungsmerkmale der Region, die über reine POI-Beschreibungen hinausgehen.
4. **Umzugstage:** Kein festes Zeitlimit pro Einzelstopp, aber max. 3-4 Stopps insgesamt zwischen Checkout (~11h) und Check-in (~16h); keine dedizierte längere Wanderung an diesen Tagen.
5. **Tagesbezogene Optional-Ziele:** Kurzer Hinweis-Block direkt am jeweiligen Tag ("Liegt auf dem Weg, nicht fest eingeplant: ..."), mit Maps-Link — nicht in einer gesammelten Extra-Sektion.

## Answer

Alle 5 Regeln in [stuetzpunkte/01_ferjukot.md](../../../stuetzpunkte/01_ferjukot.md) umgesetzt (neue Abschnitte 2 "Besonderheiten der Region" und 5 "Wanderungen", Maps-Links durchgängig, Optional-Hinweise pro Tag, Umzugstag-Hinweis in Tag 5). Gilt ab sofort als verbindliches Format für die Detailplanungs-Tickets [18](18-detailplanung-hvolsvoellur-hella.md), [19](19-detailplanung-skaftafell-hoefn.md), [20](20-detailplanung-egilsstadir.md)-[24](24-detailplanung-grundarfjordur.md).

---

## Update (08.08.2026): verbindliches Format, Stand nach Fertigstellung von 01_ferjukot.md

Die 5 Regeln oben sind weiterhin gültig, aber unvollständig — `01_ferjukot.md` wurde seither um mehrere Abschnitte, Prozessregeln und Redundanz-Bereinigungen erweitert. **Maßgeblich für die Tickets 18-24 ist ab sofort die folgende Liste**, nicht mehr die 5 Regeln allein. Referenzdokument ist die jetzige, fertige Fassung von [stuetzpunkte/01_ferjukot.md](../../../stuetzpunkte/01_ferjukot.md).

### A. Verbindliche Abschnittsstruktur (Reihenfolge und Nummerierung wie in 01_ferjukot.md)

1. **`## 1. Stützpunktspezifische Überlegungen`** — Bullets zur Logik des Stützpunkts (Standortwahl, Routenstrategie, antizyklische Planung, bewusste Auslassungen) plus die **Drohnen-Grundregel** des Stützpunkts. *Begründung: erklärt einmalig das „Warum" hinter dem Tagesplan, statt es über die Tage zu verstreuen.*
2. **`## 2. Licht & Nachthimmel (Landschaftsfotografie)`** — recherchierte Sonnenauf-/-untergangstabelle für jeden Tag des Zeitraums, abgeleitete Golden/Blue-Hour-Fenster, Dunkelheits- und Mondphasenlage für Nordlichter, sowie eine Tabelle „Motiv ↔ Tageszeit" mit Bewertung jedes geplanten Spots (passt / grenzwertig / Konflikt + Ausweichoption). *Begründung: die Reise ist fotografiegetrieben, Zeitfenster müssen gegen den Sonnenstand geprüft sein, nicht nur gegen die Fahrzeit.*
3. **`## 3. Besonderheiten der Region`** — geologische/kulturelle/historische Alleinstellungsmerkmale mit je einer verlinkten Quelle zum Vertiefen. *Begründung: Hintergrundwissen, das über reine POI-Beschreibungen hinausgeht (Regel 3 der ursprünglichen Liste).*
4. **`## 4. Wichtige Apps & Vorab-Buchungen`** — **nur** stützpunktspezifische Pflicht-Buchungen und Reservierungen; Standard-Apps nur als Einzeiler-Verweis auf die README. *Begründung: siehe Redundanzregel B1.*
5. **`## 5. Detailplanung Tag X bis Tag Y`** — ein `###`-Unterabschnitt je Tag mit Uhrzeit-Blöcken, Maps-Links, Fahrzeitangaben je Etappe, dem Block *„Liegt auf dem Weg, nicht fest eingeplant: …"* und mindestens 2 nummerierten **Tagesalternativen** (Wetter/Zeitdruck). Am Ende des Abschnitts ein kurzer Absatz, der die **Fahrzeit-Validierung** dokumentiert (siehe C1). *Begründung: Kern des Dokuments; Alternativen machen den Plan im Feld benutzbar statt nur schön.*
6. **`## 6. Pisten & Fahrzeug-Risiko (RAV4)`** — Tabelle aller relevanten F-Straßen/Pisten des Stützpunkts mit Furtenlage, Bewertung für den RAV4 und Quelle, plus kurzer Absatz zur allgemeinen Fahrzeugsituation und Verweis auf Ticket 02/26. *Begründung: das Fahrzeug ist der harte Limitierungsfaktor jeder Hochland-/Pistenplanung und muss pro Stützpunkt explizit bewertet sein.*
7. **`## 7. Wanderungen`** mit **a) Kurztouren an/zu den POIs** und **b) Top-Empfehlungen der Region** — Tabellen mit Länge, Höhenmetern, Schwere, Bewertung, Startpunkt (Maps-Link) und Charakteristik; in b) zusätzlich die Spalte **„Status im Plan"** (fest eingeplant / optional an Tag X / Alternative andernorts / rein optional). *Begründung: ursprüngliche Regel 2, ergänzt um die Status-Spalte, damit sichtbar ist, was tatsächlich verankert ist und was nur Empfehlung bleibt.*
8. **`## 8. Mögliche Alternativen (Schlechtwetter / Plan B)`** — wetterunabhängige bzw. windgeschützte Ausweichziele, jeweils mit Verweis auf die Wanderdaten in Abschnitt 7 statt Wiederholung. *Begründung: Island-Wetter erzwingt einen Plan B je Stützpunkt.*
9. **`## 9. POI-Übersicht (aus README HIGHLIGHTS_PINS)`** — Tabelle mit den Spalten **POI | Verwendet | Warum priorisiert / warum nicht**, ohne Beschreibungsspalte, mit Verweis auf die README im Vorspann. *Begründung: macht lückenlos nachweisbar, dass kein vorrecherchierter POI stillschweigend unter den Tisch gefallen ist — siehe auch B3.*
10. **`## 10. Eigene POI-Recherche: weitere Ziele im Umkreis`** — per WebSearch selbst recherchierte, in der README **nicht** enthaltene POIs im ca. 1-1,5 Std Fahrzeitradius, gefiltert nach dem Reiseprofil, mit Spalten POI | Beschreibung | Grobe Tag-Einschätzung | Empfehlung und ⭐-Markierung für besonders passende Kandidaten; übernommene Einträge werden als solche gekennzeichnet. *Begründung: die README-Liste ist eine Vorauswahl, kein Vollbild — dieser Abschnitt ist der eigene Mehrwert der Detailplanung.*

### B. Redundanz-Regeln (nicht duplizieren)

1. **Standard-App-Liste nicht wiederholen.** Veður.is, Hello Aurora, Umferdin.is, Parka.is und Bensín stehen in `README.md` (ORGANISATION_UND_APPS); in der Stützpunktdatei nur ein Einzeiler-Verweis plus die stützpunktspezifischen Pflicht-Buchungen. *Begründung: wortgleiche Doppelung veraltet sonst an zwei Stellen unterschiedlich.*
2. **Drohnen-Hinweis nur einmal.** Die Grundregel (Verbot an Hauptattraktionen, in Nationalparks und Naturschutzgebieten, lokale Schilder, Aufwinde an Schluchten) gehört als Bullet in Abschnitt 1; an den einzelnen Tagen stehen **ausschließlich echte Ausnahmen oder Zusatzinfos** (z. B. „Sigöldugljúfur: Fliegen meist möglich", oder Privatland-/Anglerhinweise am Umzugstag). *Begründung: vier fast identische Sätze pro Dokument tragen keine Information.*
3. **POI-Beschreibungen nicht aus der README kopieren.** Abschnitt 9 verweist auf die README und begründet stattdessen die Auswahlentscheidung. *Begründung: die Begründung ist der eigentliche Planungswert, die Beschreibung existiert schon.*
4. Allgemein gilt: Wenn eine Information bereits in `README.md`, `map.md` oder einem anderen Abschnitt desselben Dokuments steht, **verlinken statt wiederholen** — Ausnahme sind bewusst redundante Kurzdaten in den Wanderungstabellen (Regel 2 der ursprünglichen Liste).

### C. Prozessregeln (nicht sichtbare Abschnitte, aber verbindlich beim Erstellen)

1. **Fahrzeit-Validierung ist Pflicht, aber kein eigener Abschnitt.** Alle Etappen werden vor dem Schreiben der Uhrzeiten per Google-Distanzmatrix (bzw. REST-Fallback, siehe CLAUDE.md) geprüft; die Uhrzeiten enthalten 10-15 Min Puffer je Stopp. Dokumentiert wird das mit **einem** Absatz am Ende von Abschnitt 5, der nur die nicht in Uhrzeiten auflösbaren Erkenntnisse nennt (z. B. „Tag X ist ein 11-Stunden-Tag"). *Begründung: die Validierung gehört in die Zahlen selbst, ein Extra-Block wiederholt nur den Tagesplan.*
2. **Google-Maps-Links für jeden physisch aufsuchbaren Ort** (POIs, Supermärkte, Museen, Parkplätze, Trailheads), nicht für Straßennamen/Regionen. *Begründung: ursprüngliche Regel 1, unverändert gültig.*
3. **Kennzeichnungspflicht für unverifizierte Angaben** (CLAUDE.md): recherchierte Fakten von Einschätzungen trennen, jeweils per kursivem Hinweis unter der betroffenen Tabelle/dem Abschnitt. *Begründung: sonst ist im Feld nicht unterscheidbar, worauf man sich verlassen kann.*
4. **AllTrails-Daten über WebSearch-Snippets ziehen**, direkter WebFetch scheitert am Bot-Schutz (403); Abweichungen zwischen AllTrails-Trail und tatsächlich geplantem Weg unter der Tabelle vermerken. *Begründung: ursprüngliche Regel 2, praktische Ergänzung.*

### D. Umzugstag-Regeln (Ursache des Vík-Fehlers)

1. **Ziel-Stützpunkt und dessen Check-in-Adresse IMMER zuerst gegen `README.md` und `.scratch/island-rundreise/map.md` verifizieren**, bevor auch nur eine Zeile des Umzugstages geschrieben wird. *Begründung: In Tag 5 war ursprünglich Vík als Ziel geplant, obwohl der 2. Stützpunkt Hvolsvöllur/Hella ist — der gesamte Tagesplan war dadurch falsch.*
2. **Keine POIs verplanen, die zu den HIGHLIGHTS_PINS des ZIEL-Stützpunkts gehören.** Diese Ziele funktionieren vom neuen Stützpunkt aus antizyklisch (früh morgens/abends) deutlich besser als mittags am Umzugstag; die Begründung dafür gehört als Satz in den Umzugstag-Vorspann. *Begründung: sonst verbrennt der Umzugstag die besten Motive des Folgestützpunkts bei schlechtestem Licht.*
3. **Max. 3-4 Stopps zwischen Check-out (~11:00 Uhr) und Check-in (~16:00 Uhr), keine dedizierte längere Wanderung**, alle Stopps an oder wenige Minuten neben der Route — es wird kein Meter zurückgefahren. *Begründung: ursprüngliche Regel 4, geschärft um das Rückfahr-Verbot.*
4. **Der Großeinkauf für den neuen Stützpunkt gehört an das Ende des Umzugstages**, im günstigsten Markt in Reichweite des neuen Quartiers (recherchiert: Kette, Adresse, Öffnungszeiten, Entfernung zum Apartment). *Begründung: Kühlware soll nicht den ganzen Tag im Auto liegen, und der Markt wird zum Hausmarkt der Folgetage. **Sonderfall Ticket 19** (Skaftafell 1N + Höfn 1N, zwei Dateien, interner Umzug am 12.09.): bei nur 1 Nacht je Unterkunft ist "Hausmarkt der Folgetage" hinfällig — Einkauf hier nur bedarfsgerecht knapp halten, kein volles Großeinkaufs-Ritual.*
5. **Recherchierte Wanderdaten von POIs, die an den Ziel-Stützpunkt abgegeben wurden, nicht löschen**, sondern mit Hinweis stehen lassen, damit sie in dessen Detailplanung übernommen werden können. *Begründung: vermeidet doppelte Recherche.*

### E. Cross-Check mit dem Vorgänger-Stützpunkt (nach Fertigstellung)

Nach Fertigstellung einer Stützpunkt-Detailplanung (nicht davor — erst wenn der eigene Tagesplan steht, sind die folgenden Fragen konkret beantwortbar) einen kurzen Cross-Check gegen das fertige Dokument des **unmittelbar vorherigen** Stützpunkts durchführen (bei Ticket 19 als Vorgänger: das ganze Dokument für Überschneidungen/liegengebliebene POIs, aber die Nahtstellen-Fahrzeitprüfung speziell gegen den Höfn-Teil, da dort der Umzug zum nächsten Stützpunkt tatsächlich startet):

1. **Überschneidungen vermeiden:** Ist ein POI in beiden Dokumenten fest eingeplant?
2. **Liegengebliebene POIs übernehmen:** Im Vorgängerdokument gezielt nach Übergabe-Hinweisen suchen (Abschnitte 7 Wanderungen, 9 POI-Übersicht, 10 Eigene POI-Recherche — z.B. der Hinweis zu Nauthúsagil/Kvernufoss in `01_ferjukot.md` Abschnitt 7a), nicht nur allgemein "ob was liegengeblieben ist" prüfen.
3. **Fahrzeit-Konsistenz an der Nahtstelle:** Umzugstag-Plan beider Dokumente gemeinsam gegenlesen — keine Lücken, Ziel-Adresse/Check-in-Zeiten stimmen auf beiden Seiten überein.

*Begründung: verhindert eine Wiederholung des Vík-Fehlers und stellt sicher, dass wetter-/zeitbedingt ausgefallene POIs nicht komplett verloren gehen, sondern beim nächsten Stützpunkt erneut geprüft werden.*

### F. Zieldatei- und Abschluss-Konvention

1. **Dateiname:** `stuetzpunkte/NN_ort.md`, NN = zweistellige Stützpunktnummer aus README.md, Ort ASCII-transliteriert (Umlaute/Þ/Ð aufgelöst), Schema wie `01_ferjukot.md`. **Ticket 19 ist ein Sonderfall: zwei getrennte Dateien** (`03_skaftafell.md` + `04_hoefn.md`), keine gemeinsame Datei — auch wenn das Ticket als eine Aufgabe bearbeitet wird.
2. Nach Fertigstellung (inkl. Cross-Check und ggf. Korrekturrunde):
   - **`README.md`** beim jeweiligen Stützpunkt um die Zeile `* DETAILPLANUNG: [stuetzpunkte/NN_ort.md](stuetzpunkte/NN_ort.md)` ergänzen (wie bereits bei Stützpunkt 1, `README.md:44`).
   - **Ticket-Kopf** von `Status: open` auf `Status: resolved` setzen und einen `## Answer`-Abschnitt ergänzen (Kurzfassung des Ergebnisses + Link zur fertigen Datei).
   - **`.scratch/island-rundreise/map.md`**, Abschnitt "Decisions so far", um einen neuen Eintrag für den fertigen Stützpunkt ergänzen.
   - *Begründung: das ist die durchgehend beobachtete Dokumentations-Konvention dieses Projekts (siehe alle bisherigen Einträge in map.md) — ohne diese drei Schritte gilt ein Stützpunkt in den projektweiten Übersichten weiterhin als offen, obwohl die Datei längst existiert.*
