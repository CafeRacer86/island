Type: research
Status: resolved

## Question

Erstelle ein allgemeines Fähigkeits- und Risikoprofil für einen Toyota RAV4 (Modelljahr ca. 2024, Mietwagen, laut Vermieter F-Straßen-tauglich/freigegeben) auf isländischen F-Straßen und bei Flussdurchquerungen:

* Bodenfreiheit, Allradsystem (Vollzeit-/Zuschaltallrad, Sperrdifferential vorhanden?) und sonstige technische Eckdaten, die für Geländetauglichkeit relevant sind.
* Welche F-Straßen-Kategorien (leicht/mittel/anspruchsvoll, z.B. F-Straßen ohne größere Furten vs. solche mit tiefen/starken Flussdurchquerungen) mit diesem Fahrzeugtyp laut Vermieter-AGB und allgemeiner Erfahrung/Empfehlung grundsätzlich befahrbar bzw. zu riskant sind.
* Grobe Faustregel für maximale empfohlene Wattiefe/Furttiefe bei diesem Fahrzeugtyp, und was bei Überschreitung als Risiko gilt (Motorschaden, Versicherungsausschluss bei Flussdurchfahrten — viele isländische Mietwagenversicherungen schließen Schäden durch Flussdurchquerungen grundsätzlich aus, das sollte geprüft werden).
* Bekannte Einschränkungen/Hinweise der isländischen Straßenbehörde (Vegagerðin/road.is) zu Mietwagen-Kategorien auf F-Straßen.

Ergebnis dient als Referenz-Faustregel, die bei der späteren Detailplanung jedes Stützpunkts auf die dort konkret geplanten Pisten (z.B. F208, F225, Westfjorde-Pisten) angewendet wird — hier keine pistenspezifische Recherche, nur das allgemeine Fahrzeugprofil.

## Context

Findings: Branch `research/rav4-fahrzeugrecherche`, Commit `67827be`, Datei `research/rav4-f-road-capability.md`.

Kernaussagen: Toyota nennt keine offizielle Wattiefe für den RAV4 (kursierende "~500mm"-Angabe ist unverifiziert, nicht herstellerseitig). Der Allradantrieb ist zuschaltend (elektromagnetische Kupplung), ohne Geländeuntersetzung und ohne Sperr-/Torsen-Differential — trotz "F-Road-tauglich"-Vermarktung kein echter Geländewagen. Iceland Car Rentals schließt in den AGB Schäden durch Flussdurchquerungen/Wasserfahrten explizit von der Versicherung aus (verifizierte Primärquelle); Blue Car Rental bietet als seltene Ausnahme ein optionales Zusatzpaket ("Liability Waiver") an, das Wasser-/Flussdurchfahrtsschäden abdeckt. Praxisfazit: Flussfurten mit diesem Fahrzeug grundsätzlich meiden, unabhängig vom Versicherungsstatus.

## Answer

RAV4 (2024) gilt für die Detailplanung als Fahrzeug **ohne echte Geländereduktion/Sperrdifferential** — F-Straßen ohne nennenswerte Furten (z.B. reine Schotterpisten) sind grundsätzlich machbar, **Flussdurchquerungen sind grundsätzlich zu vermeiden**, unabhängig davon ob der Vermieter die Strecke nominell freigibt: keine verifizierte Werksangabe zur Wattiefe, on-demand-Allrad statt echtem 4x4-System, und Versicherungsausschluss für Wasserschäden bei den meisten Vermietern (Ausnahme: optionales Blue-Car-Rental-Zusatzpaket, falls dieser Vermieter genutzt wird). Konsequenz für die Detailplanung je Stützpunkt: Pisten mit bekannten Furten (z.B. F210, F233, tiefere Westfjorde-Pisten) sind bei der Routenwahl zu meiden oder es ist eine Fuß-/Brücken-Umgehung wie bereits für Landmannalaugar (F208 Nord, Fußgängerbrücke) vorzusehen; volles Detailprofil siehe `research/rav4-f-road-capability.md` auf Branch `research/rav4-fahrzeugrecherche`.

**Nachtrag/Präzisierung ([Ticket 26](26-f-strassen-flussdurchquerungen-kritische-pisten.md), 2026-08-08):** Ralf hat den Blue-Car-Rental-"Liability Waiver" tatsächlich gebucht (deckt Wasserschäden inkl. Flussdurchquerung ab). Die pauschale "grundsätzlich meiden"-Regel oben gilt damit nicht mehr uneingeschränkt: Bei Furten, die durch mehrere unabhängige Quellen übereinstimmend als **flach/kurz** dokumentiert sind, ist eine Durchquerung jetzt **grundsätzlich vertretbar**, sofern die Vor-Ort-Einschätzung (Strömung, Untergrund, aktueller Pegel) das bestätigt. Bei Furten mit unsicherem/wechselndem Flussbett oder ohne verlässliche Tiefenangabe (z.B. Þórsmörk/Krossá) bleibt die ursprüngliche Vermeidungsregel unverändert bestehen — dort geht es um ein Sicherheits-, nicht nur um ein Versicherungsrisiko. Details siehe Ticket 26.
