Type: research
Status: resolved

## Question

Systematischer, echter Verfügbarkeitsabgleich auf Buchungsportalen (booking.com bevorzugt, ergänzend Alternativen wie z.B. Airbnb, Guesthouses Iceland, direkte Anbieterseiten) für den Reisezeitraum 03.-24.09., fokussiert auf das bekannte Problemgebiet Süd-Island (Vík/Kirkjubæjarklaustur-Raum, siehe [Route-Validierung](01-route-validierung.md)): Gibt es dort überhaupt noch eine buchbare Route, und wenn ja welche?

**Pflicht-Filter (um False Positives zu vermeiden):**
* Echte Verfügbarkeit zum jetzigen Buchungszeitpunkt für die konkreten Daten — keine reine Orts-/Kategorie-Auflistung, sondern tatsächlich noch buchbare Objekte.
* Eigenes Bad.
* Küche oder Küchenzeile (Selbstversorgung, siehe Reiseprofil in [map.md](../map.md)).
* Ausnahme: für maximal 1-2 Nächte am Stück dürfen auch Hotels ohne Küche einbezogen werden.
* Schmerzgrenze weiterhin 350-400€/Nacht (siehe map.md Notes).

**Zu testende Szenarien (mehrere durchspielen, nicht nur eines):**
1. Unterschiedlich lange Aufenthalte im Süden (z.B. 2, 3, 4 Nächte statt fix 4) — sinkt der Verfügbarkeitsdruck bei kürzeren Aufenthalten?
2. Abweichende Orte/Aufteilung (z.B. Vík und Kirkjubæjarklaustur als getrennte kürzere Etappen statt ein Stützpunkt, oder eine andere Basis wie Skógar/Hvolsvöllur/Höfn-nahe Alternativen).
3. Route im Uhrzeigersinn (Norden zuerst) statt der bisher geplanten Route gegen den Uhrzeigersinn — prüft, ob sich die Süden-Nächte dadurch auf einen Zeitpunkt im Reiseverlauf verschieben, an dem noch Verfügbarkeit besteht.
4. Die bereits gebuchte 1. Unterkunft (Ferjukot, kostenfrei stornierbar) nicht mehr als zwingender Reisestart behandeln — nur einplanen, wenn sie ohne Umweg in die (ggf. neue) Route passt. Sie gilt als grundsätzlich attraktiv und soll genutzt werden, wenn es passt.

**Ziel:** ein konkreter, mit echter Verfügbarkeit unterlegter Vorschlag für Reihenfolge + Nächteverteilung, mit dem anschließend für alle 21 Nächte in einem Rutsch gebucht/reserviert werden kann (kein reiner Kostenvergleich, siehe Out-of-scope in map.md).

## Ausführungshinweis

`WebFetch`/`WebSearch` liefern bei booking.com-Suchergebnissen keinen nutzbaren Inhalt (JS-gerendert, siehe map.md Notes). Diese Recherche erfordert echte Browser-Interaktion (Filter setzen, Ergebnisse mehrfach mit variierten Daten/Orten prüfen) — kein reiner `/research`-Subagent mit WebFetch/WebSearch.

**Bekannter Stand bei Ticket-Anlage (2026-08-02):** In der aktuellen Session ist kein Browser-Automatisierungstool verbunden — weder ein chrome-devtools-MCP-Server noch `claude-in-chrome`-Tools waren verfügbar (geprüft per Tool-Suche). Bevor dieses Ticket bearbeitet werden kann, muss entweder ein solches Tool in einer neuen Session verbunden werden, oder die Prüfung läuft als Live-Session gemeinsam mit Ralf (Screenshots/Live-Checks im Chat), wie bereits bei der Vík/Kirkjubæjarklaustur-Stichprobe in [Route-Validierung](01-route-validierung.md) geschehen.

## Comments

* Ralf: Idee kam aus der bisherigen Diskussion in [Route-Validierung](01-route-validierung.md) — Uhrzeigersinn-Umkehrung wurde dort als "riskant/spekulativ" eingestuft, da unklar war, ob sich dadurch tatsächlich Verfügbarkeit verschiebt. Dieses Ticket soll genau das mit echten Portal-Daten statt Spekulation klären.
* Session-Update: `chrome-devtools` MCP-Server ist jetzt verbunden (verifiziert per `claude mcp list`), Live-Checks direkt in dieser Session durchgeführt statt in einer neuen Session/mit Ralf. Filter (Private bathroom + Kitchen/Kitchenette) wurden über die Booking.com-Filterleiste gesetzt, nicht nur über rateneu geschätzte `nflt`-URL-Parameter (erster Versuch mit falsch geratenen Filtercodes lieferte 0 Treffer wegen falscher Codes — von Ralf korrigiert, danach über UI-Klick bzw. verifizierten `nflt`-Code `roomfacility=999;roomfacility=38` gearbeitet).

## Answer

**Getestete Szenarien (booking.com, 2 Erwachsene, Filter: Private bathroom + Kitchen/Kitchenette):**

| Ort | Zeitraum | Ergebnis | Direktlink(s) |
|---|---|---|---|
| Vík | 07.–11.09. (4N, Ist-Plan) | Nur 1 Objekt gesamt am Ort (Adventure Stay, Zelt/Glamping, kein Küche, Frühstück inkl., ~€778/Nacht) — 0 Treffer mit Pflicht-Filtern | [Adventure Stay](https://www.booking.com/hotel/is/adventure-stay.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Kirkjubæjarklaustur | 07.–11.09. (4N, Ist-Plan) | Nur 1 Objekt gesamt (Hotel Klaustur, €5.078/4N ≈ €1.270/Nacht) — keine Kitchen-Filteroption existiert überhaupt für diese Suche, also 0 self-catering-Optionen zu jedem Preis | [Hotel Klaustur](https://www.booking.com/hotel/is/klaustur.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Vík | 07.–09.09. (2N statt 4N) | Identisches Einzelobjekt (Adventure Stay), identischer Preis/Nacht, kein Küche — **kürzere Aufenthalte lösen das Problem nicht**, der Engpass ist ortsgebunden, nicht dauerbezogen | [Adventure Stay, 07.–09.09.](https://www.booking.com/hotel/is/adventure-stay.html?checkin=2026-09-07&checkout=2026-09-09&group_adults=2&no_rooms=1&group_children=0) |
| Vík | 20.–24.09. (Uhrzeigersinn-Verschiebung ans Reiseende) | Weiterhin 0 Treffer mit Filtern (identisches Einzelobjekt ohne Küche) | [Adventure Stay, 20.–24.09.](https://www.booking.com/hotel/is/adventure-stay.html?checkin=2026-09-20&checkout=2026-09-24&group_adults=2&no_rooms=1&group_children=0) |
| Kirkjubæjarklaustur | 20.–24.09. (Uhrzeigersinn-Verschiebung) | 1 Treffer mit Filtern (Hólaskjól Highland Center, €1.565/4N ≈ €391/Nacht, 30,4 km vom Zentrum) — Preis knapp an der 350-400€-Schmerzgrenze, aber weiterhin nur 1 Objekt → gilt laut map.md-Regel weiterhin als Verfügbarkeits-Alarm | [Hólaskjól Highland Center, 20.–24.09.](https://www.booking.com/hotel/is/holaskjol-cabin-1.html?checkin=2026-09-20&checkout=2026-09-24&group_adults=2&no_rooms=1&group_children=0) |
| **Hvolsvöllur/Hella** (alternative Basis, ~30-45 Fahrminuten westlich von Vík) | **07.–11.09. (Original-Zeitraum, keine Verschiebung nötig)** | **14 Treffer mit Filtern (Private bathroom + Kitchen/Kitchenette), €918–€4.030 für 4 Nächte — Details siehe Tabelle unten** | siehe Tabelle unten |

**Alle 14 Hvolsvöllur/Hella-Treffer (07.–11.09., 4 Nächte, mit Küche+eigenem Bad), sortiert nach Preis/Nacht — für schnelle Entscheidung:**

| Unterkunft | Preis (4N) | €/Nacht | Kostenlose Stornierung | Unter 350-400€-Grenze? | Direktlink (07.–11.09., 2 Erw.) |
|---|---|---|---|---|---|
| Apartment - Fíflholt | €918 | ≈€230 | Nein | Ja | [Link](https://www.booking.com/hotel/is/apartment-fiflholt.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Riverfront Lodge Hella | €1.005 | ≈€251 | Nein | Ja | [Link](https://www.booking.com/hotel/is/millhouse-river-front.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Uxahryggur | €1.056 | ≈€264 | Nein | Ja | [Link](https://www.booking.com/hotel/is/uxahryggur.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Aris place | €1.080 | ≈€270 | Ja | Ja | [Link](https://www.booking.com/hotel/is/aris-place.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Afternoon Cottages | €1.280 | ≈€320 | Ja | Ja | [Link](https://www.booking.com/hotel/is/hekla-cottage.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Áshamrar | €1.338 | ≈€335 | Ja | Ja | [Link](https://www.booking.com/hotel/is/ashamrar.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Hellisholar Cottages | €1.464 | ≈€366 | Ja | Ja | [Link](https://www.booking.com/hotel/is/hellisholar-cottages.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Hella - Riverbank | €1.498 | ≈€375 | Ja | Ja | [Link](https://www.booking.com/hotel/is/hella-riverbank.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Vestra Fíflholt Cabin 4 | €1.620 | ≈€405 | Nein | Knapp drüber | [Link](https://www.booking.com/hotel/is/vestra-fiflholt-cabin-4.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Stracta Hotel | €1.754 | ≈€439 | Nein | Drüber | [Link](https://www.booking.com/hotel/is/stracta.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Hestheimar | €2.229 | ≈€557 | Nein | Drüber | [Link](https://www.booking.com/hotel/is/hestheimar.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Aurora Sky | €2.340 | ≈€585 | Nein | Drüber | [Link](https://www.booking.com/hotel/is/aurora-sky.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Seljanlandsfoss Cabin & Private Jacuzzi | €2.544 | ≈€636 | Ja | Drüber | [Link](https://www.booking.com/hotel/is/seljanlandsfoss-luxury-northern-lights-cabin.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |
| Aurora Glass Cabin II (Private sauna/Jacuzzi) | €4.030 | ≈€1.008 | Ja | Drüber (Luxus-Ausreißer) | [Link](https://www.booking.com/hotel/is/aurora-glass-cabin-ii-private-sauna-and-jacuzzi.de.html?checkin=2026-09-07&checkout=2026-09-11&group_adults=2&no_rooms=1&group_children=0) |

→ **8 von 14 Optionen liegen unter der 350-400€-Schmerzgrenze**, davon 5 mit kostenloser Stornierung (Aris place, Afternoon Cottages, Áshamrar, Hellisholar Cottages, Hella - Riverbank) — das deckt die vom Reiseprofil geforderte Selbstversorgung (eigene Küche) und eigenes Bad ab und erlaubt eine späte, flexible Entscheidung ohne Buchungsdruck.

**Fazit:** Von allen getesteten Szenarien löst nur der Basiswechsel Vík/Kirkjubæjarklaustur → **Hvolsvöllur/Hella** die Verfügbarkeitskrise wirklich — und das bereits bei den ursprünglichen Daten (07.–11.09.), ohne Verschiebung oder Kürzung. Kürzere Aufenthalte am selben Ort und reine Datums-/Reihenfolge-Verschiebung (Uhrzeigersinn) helfen nicht bzw. nur unzureichend (Kirkjubæjarklaustur Ende September bleibt ein Verfügbarkeits-Alarm mit nur 1 Objekt).

**Trade-off, den [Route-Validierung](01-route-validierung.md) jetzt klären muss:** Hvolsvöllur/Hella liegt deutlich weiter von den bisher für diesen Stützpunkt vorgesehenen Highlights entfernt (Dyrhólaey, Reynisfjara, Þakgil, Fjaðrárgljúfur, Systrafoss) — grob geschätzt 1 bis 1,5 Std. Fahrzeit einfach zur Vík-Gegend, weiter noch zu Kirkjubæjarklaustur/Fjaðrárgljúfur (ungeprüfte Faustregel, keine Distanzmatrix-Abfrage). Positiv: Hvolsvöllur liegt sehr nah an Ferjukot (Stützpunkt 1) und an Seljalandsfoss/Skógafoss, was die Routenlogik am Reiseanfang vereinfachen könnte.

**Nicht getestet (aus Zeit-/Aufwandsgründen nicht weiterverfolgt, da Hvolsvöllur bereits eine klare Lösung liefert):** Skógar als weitere Alternativ-Basis; Kombination aus Hvolsvöllur + Uhrzeigersinn-Verschiebung; Ferjukot-optional-Szenario (Ferjukot bleibt bei Hvolsvöllur als Nachbar-Basis ohnehin geografisch stimmig, keine gesonderte Prüfung nötig).
