# Muster für Stützpunkt-Detailplanungen

Einstiegspunkt für die Detailplanung der Stützpunkte 2-9 — gedacht zum Verweisen in einer neuen Session ohne Bestandskontext.

**Zuordnung Ticket → Stützpunkt** (nicht 1:1, da Ticket 19 zwei Stützpunkte abdeckt):

| Ticket | Stützpunkt(e) | Ort | Zieldatei |
|---|---|---|---|
| [18](.scratch/island-rundreise/issues/18-detailplanung-hvolsvoellur-hella.md) | 2 | Hvolsvöllur/Hella | `stuetzpunkte/02_hvolsvoellur_hella.md` |
| [19](.scratch/island-rundreise/issues/19-detailplanung-skaftafell-hoefn.md) | 3 + 4 | Skaftafell + Höfn | **zwei Dateien:** `stuetzpunkte/03_skaftafell.md` + `stuetzpunkte/04_hoefn.md` |
| [20](.scratch/island-rundreise/issues/20-detailplanung-egilsstadir.md) | 5 | Egilsstaðir | `stuetzpunkte/05_egilsstadir.md` |
| [21](.scratch/island-rundreise/issues/21-detailplanung-husavik.md) | 6 | Húsavík/Nordosten | `stuetzpunkte/06_husavik.md` |
| [22](.scratch/island-rundreise/issues/22-detailplanung-akureyri.md) | 7 | Akureyri/Eyjafjörður | `stuetzpunkte/07_akureyri.md` |
| [23](.scratch/island-rundreise/issues/23-detailplanung-hunafloi-bucht.md) | 8 | Húnaflói-Bucht | `stuetzpunkte/08_hunafloi_bucht.md` |
| [24](.scratch/island-rundreise/issues/24-detailplanung-grundarfjordur.md) | 9 | Grundarfjörður/Snæfellsnes | `stuetzpunkte/09_grundarfjordur.md` |

Für Ticket 20-24 ist der jeweils in der Tabelle darüberstehende Stützpunkt der "unmittelbare Vorgänger" für den Cross-Check (siehe unten); bei Ticket 20 betrifft die Nahtstellen-Fahrzeitprüfung speziell den **Höfn-Teil** von Ticket 19 (dort startet der Umzug), die anderen zwei Cross-Check-Punkte das ganze Ticket-19-Ergebnis.

## Referenzen (nicht dupliziert, hier nur verlinkt)

* **Struktur/Darstellung:** [stuetzpunkte/01_ferjukot.md](stuetzpunkte/01_ferjukot.md) — fertige, freigegebene Detailplanung für Stützpunkt 1, dient als Vorlage für Abschnittsaufbau, Ton und Detailgrad.
* **Verbindlicher Formatkatalog inkl. Zieldatei-Konvention, Abschluss-Schritten und Cross-Check-Prozess:** [Ticket 25, Abschnitt "Update"](.scratch/island-rundreise/issues/25-detailplanungsformat-verfeinern.md) — **maßgeblich ist der Update-Abschnitt am Dateiende, trotz `Status: resolved`** des Tickets; die 5 Regeln im oberen Ticket-Teil sind überholt. Bei jedem neuen Stützpunkt zuerst lesen.
* **Reiseprofil/Parameter:** [README.md](README.md).
* **RAV4-Fahrzeugprofil & F-Straßen:** [Ticket 02](.scratch/island-rundreise/issues/02-rav4-fahrzeugrecherche.md), [Ticket 26](.scratch/island-rundreise/issues/26-f-strassen-flussdurchquerungen-kritische-pisten.md).
* **Google-Maps-Fallback:** MCP-Server aktuell nicht verbunden, REST-Fallback siehe [CLAUDE.md](CLAUDE.md).

## Arbeits-/Zusammenarbeits-Präferenzen (aus der Ferjukot-Session)

Diese Punkte stehen bewusst getrennt vom Formatkatalog — sie beschreiben nicht, wie das Zieldokument aussehen soll, sondern wie die Zusammenarbeit beim Erstellen ablaufen soll:

1. **Grilling-Stil bei echten Präferenzentscheidungen:** eine Frage nach der anderen, mit einer klar empfohlenen Option zuerst. Nicht raten, wo Ralfs Präferenz gefragt ist — aber auch nicht bei reinen Fakten fragen, die recherchierbar sind.
2. **Fakten recherchieren, nicht aus Trainingswissen ergänzen:** WebSearch/WebFetch für Öffnungszeiten, Preise, Fahrzeiten, Trail-Daten etc. (siehe CLAUDE.md). Unverifizierte Angaben im Zieldokument kennzeichnen — auch von Ralf selbst als "nicht durch mich bestätigt" markierte Pins bleiben so gekennzeichnet, bis sie aktiv gegengeprüft wurden.
3. **Opus-Sub-Agents für größere Bau-/Korrektur-Durchgänge, aber ohne `AskUserQuestion`:** bei umfangreicher Recherche- oder Schreibarbeit (z.B. eine komplette Tagesplanung, ein größerer Korrekturdurchgang) einen Sub-Agenten mit Modell `opus` einsetzen. Sub-Agents haben in der Praxis **kein** `AskUserQuestion` zur Verfügung — trifft ein Sub-Agent deshalb notgedrungen selbst eine Präferenzentscheidung, muss er sie im Abschlussbericht explizit als eigene Entscheidung mit Begründung ausweisen; der Hauptagent legt sie Ralf danach einzeln zur Bestätigung vor, bevor sie endgültig übernommen wird (nicht stillschweigend akzeptieren).
4. **Bericht vor Umsetzung bei Bewertungsfragen:** wenn eine Aufgabe eher "kritisch bewerten/Lücken finden" ist (z.B. ein Cross-Check) statt "klar umsetzen", zuerst nur einen Bericht liefern und auf Freigabe warten, bevor direkt in Dateien geschrieben wird. Bei eindeutigen, bereits abgestimmten Korrekturen darf direkt geschrieben werden.
5. **Vorschläge sind keine Vorentscheidungen.** Ralf weicht regelmäßig bewusst von gelieferten Shortlists/Empfehlungen ab (z.B. Unterkunftsauswahl außerhalb der Top-Kandidaten). Optionen liefern und begründen, aber keine Auswahl als bereits beschlossen behandeln.

## Cross-Check mit dem Vorgänger-Stützpunkt

Der vollständige Prozess (3 Prüfpunkte: Überschneidungen, liegengebliebene POIs, Fahrzeit-Nahtstelle) steht in [Ticket 25, Abschnitt E](.scratch/island-rundreise/issues/25-detailplanungsformat-verfeinern.md) — dort nachlesen, hier nicht dupliziert. Grundregel: **am Ende**, nach fertiger eigener Detailplanung, gegen das fertige Dokument des in der Tabelle oben genannten unmittelbaren Vorgängers.

## Ablauf-Checkliste für eine neue Session

1. Diese Datei + verlinkten Formatkatalog (Ticket 25, insb. Abschnitt F "Zieldatei- und Abschluss-Konvention") + `01_ferjukot.md` lesen.
2. Zugehöriges Detailplanungs-Ticket lesen, README-HIGHLIGHTS_PINS für diesen Stützpunkt als Ausgangsbasis, Zieldateiname aus der Tabelle oben übernehmen.
3. Vor dem Umzugstag: Ziel-Stützpunkt und Check-in-Adresse gegen README.md und map.md verifizieren, Ziel-HIGHLIGHTS_PINS tabu (Ticket 25 Abschnitt D1-D2) — nicht erst am Ende merken, dass das Ziel falsch war.
4. Detailplanung erstellen (Abschnittsstruktur/Redundanz-/Prozessregeln aus Ticket 25 Abschnitt A-D einhalten).
5. Cross-Check mit dem Vorgänger-Stützpunkt durchführen (Ticket 25 Abschnitt E).
6. Bei Bedarf: kritischen Opus-Cross-Check über das eigene Ergebnis (Lücken/Konsistenz/Vereinfachung) wie bei Stützpunkt 1 — Bericht zuerst, dann Korrekturen in Rücksprache.
7. Abschluss-Schritte (Ticket 25 Abschnitt F2): README-`DETAILPLANUNG`-Zeile ergänzen, Ticket-Status auf `resolved` + `## Answer` setzen, Eintrag in map.md "Decisions so far" ergänzen.
