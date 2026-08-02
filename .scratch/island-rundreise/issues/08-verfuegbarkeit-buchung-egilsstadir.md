Type: research
Status: resolved

## Question

Echte Buchungsportal-Verfügbarkeitsprüfung (booking.com bevorzugt, Pflicht-Filter: eigenes Bad, Küche/Küchenzeile — Ausnahme wie üblich bei max. 1-2 Nächten auch ohne Küche, Schmerzgrenze 350-400€/Nacht) für Stützpunkt 4 **Egilsstaðir**, aktuell geplant 2 Nächte, 13.-15.09.2026 (Tag 11-13), 2 Erwachsene.

**Ziel:** eine tatsächlich buchbare Unterkunft finden und Ralf eine kurze, klar priorisierte Shortlist (mit Direktlinks) zum eigenen Buchen übergeben — nicht nur eine Verfügbarkeitseinschätzung. Nächtezahl/Struktur kritisch gegen die Trefferzahl prüfen (siehe map.md-Regel: <2-3 Treffer oder alle über der Schmerzgrenze = Verfügbarkeits-Alarm, dann Struktur überdenken statt höheren Preis akzeptieren).

**Kleiner Ausblick nach vorne (bei fehlenden Angeboten):** falls Egilsstaðir für 2 Nächte keine tragfähige Buchung hergibt, kurz gegenprüfen, ob eine Verschiebung von 1 Nacht zum direkt benachbarten Stützpunkt 5 (Mývatn/Reykjahlíð, aktuell 4 Nächte, 15.-19.09.) — in beide Richtungen (Egilsstaðir verkürzen zugunsten Mývatn, oder verlängern zulasten Mývatn) — bessere Verfügbarkeit ergäbe. Keine vollständige Neuvalidierung von Mývatn nötig, nur ein grober Verfügbarkeits-Gegencheck für die verschobene Nächtezahl an beiden Orten.

## Ausführungshinweis

`chrome-devtools` MCP-Server nutzen (siehe CLAUDE.md für Ablauf: Cookie-Banner/Sign-in-Modal wegklicken, Filter `nflt=roomfacility%3D999%3Broomfacility%3D38` für Private bathroom + Kitchen/Kitchenette anhängen, Ergebnisse per `evaluate_script` extrahieren statt `take_snapshot`).

## Comments

* Live-Check (2026-08-02), booking.com, 13.-15.09.2026 (2N), 2 Erwachsene, Filter Private bathroom + Kitchen/Kitchenette: **8 Treffer insgesamt** (kein Vík-artiger Engpass) — kein Verfügbarkeits-Alarm. Lookahead auf Mývatn/Reykjahlíð daher nicht nötig, da bereits mehrere Optionen unter der Schmerzgrenze liegen.

| Unterkunft | Preis (2N) | €/Nacht | Kostenlose Stornierung | Unter 350-400€? | Direktlink (13.-15.09., 2 Erw.) |
|---|---|---|---|---|---|
| Móðir Jörð Organic Farm Guesthouse (Vallanes) | €520 | ≈€260 | Ja | Ja | [Link](https://www.booking.com/hotel/is/modir-jord-organic-b-amp-b-in-vallanes.de.html?checkin=2026-09-13&checkout=2026-09-15&group_adults=2&no_rooms=1&group_children=0) |
| Stormur Cottages | €617 | ≈€309 | Ja | Ja | [Link](https://www.booking.com/hotel/is/stormur-cottages.de.html?checkin=2026-09-13&checkout=2026-09-15&group_adults=2&no_rooms=1&group_children=0) |
| Eiðar - Apartments | €601 | ≈€301 | Nein | Ja | [Link](https://www.booking.com/hotel/is/eidar-apartments.de.html?checkin=2026-09-13&checkout=2026-09-15&group_adults=2&no_rooms=1&group_children=0) |
| Eidavellir Apartments and Rooms | €659 | ≈€330 | Nein | Ja | [Link](https://www.booking.com/hotel/is/vallnaholt-8.de.html?checkin=2026-09-13&checkout=2026-09-15&group_adults=2&no_rooms=1&group_children=0) |
| Lagarfell Studios | €810 | ≈€405 | Nein | Knapp drüber | [Link](https://www.booking.com/hotel/is/lagarfell-homestay.de.html?checkin=2026-09-13&checkout=2026-09-15&group_adults=2&no_rooms=1&group_children=0) |
| Media Luna Guesthouse | €898 | ≈€449 | Ja | Drüber | [Link](https://www.booking.com/hotel/is/media-luna-guesthouse.de.html?checkin=2026-09-13&checkout=2026-09-15&group_adults=2&no_rooms=1&group_children=0) |
| Deluxe Family Apartment / Seydisfjördur Apartment | €1.515-1.731 | ≈€757-865 | Nein | Weit drüber (große Apartments, 3 Schlafzimmer) | – |

## Answer

Ralf hat **Stormur Cottages** (Hvammur 2, 701 Vallanes) fest gebucht, mit Stornooption: Check-in So. 13.09. 17:00-23:00, Check-out Di. 15.09. 07:00-11:00, 2 Nächte, 2 Erwachsene, 1 Bungalow. Damit ist Stützpunkt 4 komplett gebucht.

## Interessen-Passungs-Check (2026-08-02, Google Distance Matrix + WebSearch)

Fahrzeiten ab Egilsstaðir zu den 10 HIGHLIGHTS_PINS (README):

| Ziel | Distanz | Fahrzeit (einfach) |
|---|---|---|
| Rjúkandi Waterfall | direkt an der Ringstraße | ~0 (kein Umweg) |
| Seyðisfjörður (inkl. Gufufoss) | 26.7 km | 27 Min |
| Hengifoss / Litlanesfoss | 35.5 km | 28 Min |
| Mjóifjörður (Klifbrekkufossar, Wrack) | 40.6 km | 58 Min |
| Stuðlagil Canyon | 71.7 km | 59 Min |
| Dalatangi | 55.1 km | 1 Std 25 (über Mjóifjörður hinaus) |
| Álftafjörður/Djúpivogur (Hænubrekkufoss-Gegend) | 84.6 km | 1 Std 21 |

**Wichtiger Fund:** Die Fahrzeit Hoffell→Egilsstaðir (199 km, 2 Std 54, vermutlich über den Öxi-Pass, Route 939) deckt sich mit der Lage von **Hænubrekkufoss** (an der Westseite des Öxi-Passes) — dieser Wasserfall lässt sich am Umzugstag Stützpunkt 3→4 unterwegs mitnehmen, braucht also keine eigene Egilsstaðir-Zeit (analog zu Fjaðrárgljúfur beim vorherigen Umzug).

**Mjóifjörður/Dalatangi (Road 953, Mjóafjardarvegur):** Recherche bestätigt: steile, schmale Schotterstraße mit Steigungen bis 18%, Abgründe zum Meer, **explizit nur für 4WD empfohlen** (2WD wird abgeraten), nur im Sommer offen. Ein Ausflug dorthin (inkl. Klifbrekkufossar-Wasserfälle und Schiffswrack, optional weiter bis zum abgelegenen Leuchtturm Dalatangi) ist an sich ein **ganzer Tag** — nicht mit anderen Zielen kombinierbar.

**Stuðlagil Canyon:** Recherche zeigt, der Canyon ist mittlerweile **touristisch stark frequentiert** (Mai-September Hauptsaison, "usually very busy") — steht damit leicht im Spannungsverhältnis zum Reiseprofil-Wunsch "Vermeidung von Touristenmassen", ist aber als ikonischer türkisfarbener Canyon mit Basaltsäulen ein starkes Fotomotiv; früher Vormittag (vor 10 Uhr) empfohlen, um die Massen zu umgehen. Hin- und Rückweg + Wanderung (Ostseite, empfohlen) ca. 2-3 Std gesamt.

**Bewertung für 2 Nächte (≈1,5 echte Tage zwischen Ankunfts- und Abreisetag):**
* **Gut machbar an einem Tag:** Stuðlagil (früh morgens, 2-3 Std) + Hengifoss/Litlanesfoss (leichte bis mittlere Wanderung, passt zum 300-400 Hm-Profil) + Seyðisfjörður/Gufufoss (kurzer Abstecher, 27 Min) — deckt die drei zugänglichsten und fotogensten Ziele ab.
* **Nicht mehr realistisch daneben:** Mjóifjörður/Dalatangi — das ist ein eigener ganzer Tag auf einer anspruchsvollen Straße, mit 2 Nächten (effektiv 1 voller Zwischentag) nicht mehr unterzubringen, ohne Stuðlagil/Hengifoss zu opfern.
* Rjúkandi und Hænubrekkufoss fallen ohnehin als Durchfahrt-Stopps an (Ringstraße bzw. Umzugstag), kosten keine zusätzliche Zeit.

**Fazit:** 2 Nächte sind für das **zugängliche Hauptcluster** (Stuðlagil, Hengifoss/Litlanesfoss, Seyðisfjörður/Gufufoss) angemessen und ausreichend — dieses Cluster passt gut zum Reiseprofil (Fotografie, leichte Wanderung). Die abgelegenen Ziele Mjóifjörður und Dalatangi (die eigentlich am besten zum "Vermeidung von Touristenmassen"-Wunsch passen würden) sind mit 2 Nächten bewusst nicht erreichbar — eine Verlängerung auf 3 Nächte (zulasten von Mývatn/Reykjahlíð, siehe Lookahead in der Frage oben) wäre nötig, um sie mitzunehmen. Da Mývatn/Reykjahlíð selbst ein dichtes 4-Nächte-Cluster mit vielen Highlights ist (Dettifoss, Hverir, Krafla etc.), würde eine Nacht-Umverteilung dort spürbar wehtun — ohne expliziten Wunsch von Ralf nach den abgelegenen Fjorden empfehle ich, bei 2 Nächten zu bleiben und Mjóifjörður/Dalatangi bewusst zu opfern.
