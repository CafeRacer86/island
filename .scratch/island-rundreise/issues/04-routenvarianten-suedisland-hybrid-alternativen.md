Type: research
Status: resolved
Blocks: 01

## Question

Aufbauend auf [Buchungsportal-Verfügbarkeitsszenarien Süd-Island](03-buchungsportal-verfuegbarkeitsszenarien.md) und der Diskussion in [Route-Validierung](01-route-validierung.md): Stelle mehrere konkrete, vollständige Routenvarianten für die Süd-Island-Passage auf, jeweils mit Nächteverteilung und einer kurzen Shortlist tatsächlich verfügbarer, buchbarer Unterkünfte pro Ort/Zeitraum.

**Pflicht-Filter für jede Unterkunfts-Shortlist (siehe map.md Notes):** eigenes Bad (kein Gemeinschaftsbad — bei Ticket 03 hat sich der automatisierte "Private bathroom"-Filter von booking.com bei Hólaskjól Highland Center als unzuverlässig erwiesen, Ralf hat das live gegengeprüft und ein Gemeinschaftsbad vorgefunden; Zimmertyp/-beschreibung deshalb bei jedem Kandidaten manuell auf "private"/"ensuite" vs. "shared"/"communal" bathroom prüfen, nicht nur den Filter-Facet vertrauen), Küche/Küchenzeile, Schmerzgrenze 350-400€/Nacht, idealerweise kostenlose Stornierung (kein Ausschlusskriterium, aber in der Shortlist markieren).

**Zu prüfende Varianten:**

1. **Gegen den Uhrzeigersinn (Ist-Struktur)** mit **Hvolsvöllur/Hella statt Vík/Kirkjubæjarklaustur** als Stützpunkt 2, 07.–11.09. — als Baseline bereits durch Ticket 03 mit Shortlist belegt, hier nur nochmal referenzieren/übernehmen, keine Neurecherche nötig.
2. **Hybrid-Option:** Stützpunkt 2 (Hvolsvöllur/Hella, ggf. mit reduzierter Nächtezahl) + Stützpunkt 3 (Höfn/Skaftafell, aktuell 2 Nächte) um 1-2 Nächte verlängert bzw. so verschoben, dass die östlichen Highlights von Stützpunkt 2 (Þakgil, Fjaðrárgljúfur, Eldgjá, Systrafoss, Kerlingarfjöll/Hveradalir, Langisjór — laut Distanzcheck von Hella aus ~2h+ einfache Fahrt, kaum tagesausflugstauglich) stattdessen von Kirkjubæjarklaustur/Skaftafell-Nähe aus abgedeckt werden. Prüfen: ist dafür in Kirkjubæjarklaustur (oder einem noch näheren Ort) für die dann nötigen 1-2 zusätzlichen Nächte überhaupt etwas mit den Pflicht-Filtern buchbar (Ticket 03 fand für Kirkjubæjarklaustur am 07.–11.09. NICHTS mit Küche — ggf. andere/kürzere Zeiträume oder Nachbarorte wie Foss á Síðu, Skaftárhreppur testen)? Falls ja: Nächteverteilung + Shortlist. Falls nein: als nicht tragfähig dokumentieren.
3. **Weitere Alternativ-Basen im Süden** neben Hvolsvöllur/Hella testen (z.B. Skógar, Foss á Síðu, Kirkjubæjarklaustur-Umland/Skaftárhreppur allgemein statt nur der Ortschaft selbst) — jeweils mit Distanz-Grobcheck zu den Haupt-Highlights und Verfügbarkeits-Shortlist.
4. **Im Uhrzeigersinn** wurde in Route-Validierung bereits geprüft und verworfen (löst Süden nicht, verschlechtert Westfjorde-Süd) — hier nur noch offen: falls eine der obigen Süd-Varianten (Hybrid oder weitere Alternativ-Basis) eine andere Nächteverteilung als der Ist-Plan ergibt, kurz gegenchecken, ob sich dadurch die Uhrzeigersinn-Rechnung für die übrigen Stützpunkte ändert — nur falls eine der Süd-Varianten das nahelegt, sonst nicht vertiefen.

**Ergebnis:** Für jede tragfähige Variante eine kompakte Tabelle (Ort, Zeitraum, Nächte, 2-4 konkrete Unterkunfts-Kandidaten mit Preis/Nacht, Stornierbarkeit, Direktlink), damit Ralf am Ende zwischen den Varianten auswählen kann, ohne selbst nachzurecherchieren.

**Pflicht-Cross-Check (Ralf, 2026-08-02):** Nicht nur den Süden isoliert validieren. Sobald eine Variante für den Süden als grundsätzlich valide gilt (Interessen-Passung + Verfügbarkeit stimmen), **muss geprüft werden, ob sie die Termine der übrigen Stützpunkte verschiebt** (jede Nächtezahl-Änderung am Süd-Stützpunkt bzw. am Stützpunkt Höfn/Skaftafell schiebt alle nachfolgenden Stützpunkt-Zeiträume) — und falls ja, für **jeden dadurch verschobenen Stützpunkt** ein schneller Verfügbarkeits-Gegencheck mit denselben Pflicht-Filtern (eigenes Bad, Küche, Schmerzgrenze) am neuen Termin, analog zum Uhrzeigersinn-Check in [Route-Validierung](01-route-validierung.md) (dort hatte die Verschiebung Westfjorde-Süd von 1 auf 0 Treffer verschlechtert — genau solche Kettenreaktionen müssen hier für jede Variante ausgeschlossen bzw. dokumentiert werden, bevor sie Ralf als Option vorgeschlagen wird). Eine Variante, die den Süden löst, aber einen anderen Stützpunkt neu in einen Verfügbarkeits-Alarm schiebt, gilt nicht als tragfähig gelöst — das muss in der Ergebnis-Tabelle transparent vermerkt werden, nicht stillschweigend übergangen.

## Comments

* Ausgegliedert aus [Route-Validierung](01-route-validierung.md) am 2026-08-02: Ralf möchte vor der finalen Entscheidung mehrere ausgearbeitete Routenoptionen mit konkreten, filterkonformen Unterkunfts-Shortlists sehen statt einer abstrakten Ja/Nein-Bewertung einzelner Szenarien.
* Technischer Hinweis für die Bearbeitung: `chrome-devtools` MCP-Server nutzen (siehe CLAUDE.md-Abschnitt "Booking.com-Suchen mit chrome-devtools" für den verifizierten Filter-Workflow inkl. `nflt=roomfacility%3D999%3Broomfacility%3D38` für Bad+Küche) — aber Bad-Angabe pro Kandidat trotzdem stichprobenartig auf der Objektseite gegenchecken, siehe Warnhinweis oben.
* Bearbeitet 2026-08-02, `chrome-devtools` MCP-Server in dieser Session verbunden und direkt genutzt (kein neuer Session-Start nötig).

## Answer

**Ergebnis: Variante 1 (Hvolsvöllur/Hella, unverändert 07.–11.09., 4 Nächte, bereits durch Ticket 03 mit 14-Treffer-Shortlist belegt) bleibt die einzige tragfähige Süd-Lösung.** Hybrid-Option und weitere Alternativ-Basen wurden geprüft und als nicht tragfähig verworfen:

| Variante | Getestet | Ergebnis |
|---|---|---|
| 2. Hybrid: Skaftafell-Gebiet als verlängerter Teil von Stützpunkt 3, 09.–13.09. (4N) | `Skaftafell, Iceland`, Filter Bad+Küche | Nur 2 Objekte gesamt, beide weit über Schmerzgrenze: Skaftafell Lodges (€2.588/4N ≈ €647/Nacht), Klettasel Villa (€11.335/4N ≈ €2.834/Nacht, Luxus-Ausreißer) |
| 2. Hybrid: Höfn als verlängerter Teil von Stützpunkt 3, 09.–13.09. (4N) | `Höfn, Iceland`, Filter Bad+Küche | 0 Treffer |
| 2. Hybrid, Referenz: Höfn im Ist-Zeitraum 11.–13.09. (2N, unverändert) | `Höfn, Iceland`, Filter Bad+Küche | Nur 3 Objekte, keines klar unter der Schmerzgrenze bei Hochrechnung auf 350-400€/Nacht (Heppa Apartments ≈€728/Nacht; HH Gisting ≈€398/Nacht, aber Filterzuverlässigkeit fraglich, siehe Warnhinweis Ticket 03 zu Bad-Angaben; Glacier World Hoffell ≈€470/Nacht) — **Höfn/Skaftafell ist selbst im Ist-Zeitraum bereits ein dünner Markt**, eine Verlängerung würde das Problem eher verschärfen als lösen. |
| 2. Hybrid: Kirkjubæjarklaustur für kürzeres Fenster 09.–11.09. (2N statt 4N) | `Kirkjubæjarklaustur, Iceland`, ohne Filter (Facet-Check) | Kein "Küche"-Filter-Facet vorhanden — bestätigt Ticket-03-Befund, dass im Ort grundsätzlich keine Unterkunft mit Küche gelistet ist, unabhängig vom Zeitraum. Nur 2 Objekte insgesamt am Ort. |
| 3. Alternativ-Basis Skógar, 07.–11.09. (4N) | `Skógar, Iceland`, Filter Bad+Küche | Nur 1 Treffer (Aurora Glass Cabin II, €4.030/4N ≈ €1.008/Nacht, Luxus-Ausreißer, identisch mit einem bereits in Ticket 03 bei Hvolsvöllur/Hella gefundenen Objekt — geografisch offenbar näher an Skógar geocodiert) |
| 3. Alternativ-Basis Foss á Síðu, 09.–11.09. (2N) | `Foss á Síðu`, Filter Bad+Küche | 0 Treffer (auch ohne Filter keine gelisteten Objekte an diesem Ort) |
| 3. Alternativ-Basis Skaftárhreppur (Umland allgemein) | `Skaftárhreppur` | Ortsname von Booking.com nicht erkannt (Fehlerseite) — keine gesonderte Suche möglich, Umland wird bereits über die o.g. Einzelort-Suchen (Kirkjubæjarklaustur, Skaftafell, Foss á Síðu) abgedeckt |

**4. Uhrzeigersinn-Rückcheck:** entfällt — keine der geprüften Varianten liefert eine von Ticket 03 abweichende Nächteverteilung, die Struktur bleibt Hvolsvöllur/Hella 07.–11.09. (4N) unverändert zur bereits akzeptierten Lösung.

**Pflicht-Cross-Check (Kettenreaktion auf nachfolgende Stützpunkte):** entfällt aus demselben Grund — da die Süd-Lösung (Hvolsvöllur/Hella, 07.–11.09., 4N) identisch zur bereits in Ticket 03 gefundenen Baseline bleibt und keine Nächtezahl/Termine anderer Stützpunkte verschiebt, gibt es keine Verschiebung gegenzuprüfen.

**Fazit für [Route-Validierung](01-route-validierung.md):** Die Süd-Frage ist damit abschließend geklärt — Stützpunkt 2 wird **Hvolsvöllur/Hella statt Vík/Kirkjubæjarklaustur**, 07.–11.09., unverändert 4 Nächte, mit der 14-Treffer-Shortlist aus Ticket 03. Der einzig verbleibende offene Punkt ist der bereits in Ticket 03 benannte Fahrzeit-Trade-off (östliche Highlights wie Þakgil, Fjaðrárgljúfur, Eldgjá, Systrafoss, Kerlingarfjöll/Hveradalir, Langisjór werden von Hvolsvöllur/Hella aus kaum noch tagesausflugstauglich erreichbar) — dieser Trade-off wird akzeptiert, da keine der geprüften Alternativen (Hybrid-Verlängerung, weitere Alternativ-Basen) eine bessere, gleichzeitig buchbare Lösung bietet. Zusatzbefund (nicht Teil dieses Tickets, aber relevant für die spätere Verfügbarkeitsprüfung von Stützpunkt 3): Höfn/Skaftafell zeigt bereits im Ist-Zeitraum (11.–13.09., 2N) nur 3 Treffer mit fraglicher Filterzuverlässigkeit — sollte bei der späteren dedizierten Verfügbarkeitsprüfung dieses Stützpunkts (siehe map.md "Not yet specified") mit besonderer Sorgfalt (Bad-Angabe manuell gegenchecken) behandelt werden.
