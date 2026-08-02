Type: research
Status: resolved

## Question

Echte Buchungsportal-Verfügbarkeitsprüfung (booking.com bevorzugt, Pflicht-Filter: eigenes Bad, Küche/Küchenzeile — Schmerzgrenze 350-400€/Nacht) für Stützpunkt 8 **Grundarfjörður/Snæfellsnes**, 2 Nächte, 22.-24.09.2026 (Tag 20-22, Abreisetag), 2 Erwachsene.

Diese Nächtezahl/dieser Zeitraum wurde in [Route-Validierung Rest](10-route-validierung-rest.md) festgelegt (3N→2N reduziert zugunsten des Blönduós-Stopps) und ist seither nie gegen echte Verfügbarkeit geprüft worden — bislang nur als "unverändert" mitgeführt, auch nach der Nord-Neustrukturierung in [Nord-Route neu strukturieren](12-nord-route-neustrukturierung.md).

**Ziel:** eine tatsächlich buchbare Unterkunft finden und Ralf eine kurze, klar priorisierte Shortlist (mit Direktlinks) zum eigenen Buchen übergeben — nicht nur eine Verfügbarkeitseinschätzung. Rückflug ist fix Do. 24.09., 16:10 Uhr ab Keflavík (Grundarfjörður→Airport 218 km/2 Std 46) — Check-out/Abfahrt am 24.09. muss das berücksichtigen, ändert aber nichts an der Buchungssuche selbst.

## Ausführungshinweis

`chrome-devtools` MCP-Server nutzen (siehe CLAUDE.md für Ablauf: Cookie-Banner/Sign-in-Modal wegklicken, Filter `nflt=roomfacility%3D999%3Broomfacility%3D38` für Private bathroom + Kitchen/Kitchenette anhängen, Ergebnisse per `evaluate_script` extrahieren statt `take_snapshot`).

## Answer

Echte Booking.com-Verfügbarkeitsprüfung 22.-24.09.2026 (2N), Filter Küche+eigenes Bad: **13 Treffer** für Grundarfjörður/Snæfellsnes — deutlich mehr als beim Verfügbarkeits-Alarm bei Höfn/Skaftafell, aber Median-Preis liegt klar höher als Süd-Island (viele Luxus-Ferienhäuser €500-1.080/Nacht). **Kein Verfügbarkeits-Alarm**, ausreichend Auswahl unterhalb der Schmerzgrenze vorhanden.

**Shortlist (priorisiert, Küche + eigenes Bad, kostenlose Stornierung):**

1. **Guesthouse Hof**, Grundarfjörður — €360 gesamt / 2N (**€180/Nacht**), Apartment mit Meerblick, 3 SZ, Küche, kostenlose Stornierung. [Link](https://www.booking.com/hotel/is/guesthouse-hof.de.html?checkin=2026-09-22&checkout=2026-09-24&group_adults=2&no_rooms=1&group_children=0)
2. **Dis Cottages**, Grundarfjörður — €456 gesamt / 2N (**€228/Nacht**), Apartment mit 1 SZ, Küche, Klimaanlage. [Link](https://www.booking.com/hotel/is/dis-cottages.de.html?checkin=2026-09-22&checkout=2026-09-24&group_adults=2&no_rooms=1&group_children=0)
3. **Stöð Guesthouse and Apartments**, Grundarfjörður — €553 gesamt / 2N (**€276,50/Nacht**), Apartment mit 1 SZ, knapp unter der Schmerzgrenze. [Link](https://www.booking.com/hotel/is/solvellir-13-guesthouse-and-apartments.de.html?checkin=2026-09-22&checkout=2026-09-24&group_adults=2&no_rooms=1&group_children=0)

Restliche Treffer (Lysuholl, Kambur Cottages, Windy Guesthause, Arnarstapi Hotel, Miðhús, Lárubúð, sowie mehrere Luxus-Ferienhäuser wie Oxl/Lava House/Glass House) liegen über €300-1.080/Nacht oder haben keine eindeutige eigene Küche — nicht in die Shortlist aufgenommen.

**Hinweis Abreisetag:** Rückflug fix Do. 24.09., 16:10 Uhr ab Keflavík; Grundarfjörður→Flughafen ca. 218 km/2 Std 46 — Check-out/Abfahrt am 24.09. entsprechend früh einplanen (ändert nichts an obiger Shortlist, nur an der Tagesplanung des Abreisetags).

**Gebucht:** Eiðhús Apartments, Snæfellsnesvegur, 311 Vegamót, 22.-24.09., 2 Nächte, 2 Erwachsene, 1 Apartment. Vegamót liegt auf der Snæfellsnes-Halbinsel nahe Grundarfjörður (an der Ringstraße/Snæfellsnesvegur), war nicht Teil der Grundarfjörður-Suchtreffer (anderer Suchbegriff), aber passt geografisch zum Stützpunkt. Check-in per Schlüsselschließfach vor Ort. Preis nicht recherchiert (direkt von Ralf gebucht).
