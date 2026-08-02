Type: task
Status: closed (out of scope)

## Question

Die in [Route-Validierung](01-route-validierung.md) final entschiedene Struktur (3N Hvolsvöllur/Hella, 07.-10.09. + 1N Fosshotel Nupar/Kálfafell, 10.-11.09.) weicht von den bisher tatsächlich geprüften Buchungszeiträumen ab: [Buchungsportal-Verfügbarkeitsszenarien Süd-Island](03-buchungsportal-verfuegbarkeitsszenarien.md) hat die Hella-Shortlist für den vollen 4-Nächte-Zeitraum (07.-11.09.) geprüft, [Split-Variante](05-split-variante-hvolsvoellur-kirkjubaejarklaustur.md) hat Fosshotel Nupar für 2 Nächte (09.-11.09.) geprüft — nicht für die jetzt benötigten 3N bzw. 1N.

Auf booking.com (mit `chrome-devtools`, Filter Bad+Küche für Hella, siehe CLAUDE.md-Workflow) real gegenprüfen:

* Sind aus der bestehenden 14-Treffer-Hella-Shortlist genug Optionen auch für nur 3 Nächte (07.-10.09.) buchbar (Mindestaufenthalt-Regeln können bei kürzeren Zeiträumen abweichen)?
* Ist Fosshotel Nupar (oder eine gleichwertige Alternative mit eigenem Bad) für nur 1 Nacht (10.-11.09.) buchbar?

**Ergebnis:** Bestätigung (mit Direktlinks) oder Alarm, falls einer der beiden kürzeren Zeiträume entgegen der Erwartung nicht buchbar ist — dann muss [Route-Validierung](01-route-validierung.md) die Nächteverteilung nochmal anpassen.

## Comments

* Ausgegliedert aus [Route-Validierung](01-route-validierung.md) am 2026-08-02.

## Out of scope (2026-08-02)

Ralf hat sich gegen den Kálfafell-Stopp entschieden (4N durchgehend Hvolsvöllur/Hella, dann direkt weiter nach Skaftafell/Höfn). Damit entfällt die Notwendigkeit, 3N-Hella- bzw. 1N-Nupar-Teilzeiträume zu verifizieren — die ursprünglich für den vollen 4-Nächte-Zeitraum geprüfte Hella-Shortlist ([Buchungsportal-Verfügbarkeitsszenarien Süd-Island](03-buchungsportal-verfuegbarkeitsszenarien.md)) gilt unverändert, Fosshotel Nupar wird nicht gebucht.
