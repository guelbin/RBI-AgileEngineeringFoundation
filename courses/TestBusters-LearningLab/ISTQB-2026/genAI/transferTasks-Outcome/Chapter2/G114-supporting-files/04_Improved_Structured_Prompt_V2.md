# G114 — Structured Prompt V2

## Rolle

Handle als Testmanager und analysiere die Testausführungsergebnisse für ToolShop Holtesting.

## Eingabe

Verwende ausschließlich die beigefügte Datei
`Monitoring_Logauszuege_day03-day05.md`.

Die Datei enthält die Ausführungszusammenfassungen und Open-Defect-Tabellen aus jeweils 15 Test-Suite-Berichten für `day03`, `day04` und `day05`.

Erfinde keine Zahlen, Defect-IDs, Statusangaben, Severity-Angaben oder Zusammenhänge. Wenn eine Information nicht eindeutig aus der Quelle hervorgeht, kennzeichne sie als „Nicht eindeutig aus der Quelle ableitbar“.

## Berechnungsregeln

Berechne für jede Testsuite und jeden Tag:

- Planned = Passed + Failed + Blocked + Not Executed
- Execution Progress = (Passed + Failed + Blocked) / Planned × 100
- Pass Rate = Passed / (Passed + Failed) × 100

Blocked und Not Executed dürfen nicht in den Nenner der Pass Rate aufgenommen werden.

Falls `Passed + Failed = 0` ist, gib für die Pass Rate „N/A“ an.

Runde Prozentwerte auf eine Nachkommastelle.

## Aufgaben

1. Erstelle für `day03`, `day04` und `day05` eine Suite-Level-Metriktabelle mit:

   - Test Suite
   - Planned
   - Passed
   - Failed
   - Blocked
   - Not Executed
   - Execution Progress
   - Pass Rate
   - Risk Flag

2. Berechne für jeden Tag die Gesamtwerte:

   - Planned
   - Passed
   - Failed
   - Blocked
   - Not Executed
   - Execution Progress
   - Pass Rate

3. Vergleiche die drei Tage und beschreibe die Entwicklung des Testfortschritts.

4. Analysiere die Defect-Trends:

   - Unique Open Defect IDs
   - New IDs gegenüber dem vorherigen Tag
   - Recurring IDs gegenüber dem vorherigen Tag
   - Unresolved High-Severity Defects

5. Prüfe bei Defect-IDs zusätzlich Summary, Severity, Related Story und Status.

   Wenn dieselbe Defect-ID in verschiedenen Testsuiten mit unterschiedlichen Summaries oder Severity-Angaben vorkommt, kennzeichne sie als „Ambiguous Defect Reference“. Verwende sie nicht ohne Hinweis als eindeutigen Nachweis für einen Defect-Trend.

6. Kennzeichne alle Testsuiten mit mindestens einem Blocked- oder Not-Executed-Test. Nenne für jede markierte Testsuite die genaue Anzahl der Blocked- und Not-Executed-Tests.

7. Schlage genau zwei Teststeuerungsmaßnahmen vor. Begründe jede Maßnahme ausschließlich mit den angegebenen Metriken und Defects.

8. Erstelle:

   - eine stakeholdergerechte Zusammenfassung
   - die Metriktabellen
   - eine Defect-Trend-Übersicht
   - eine Übersicht der gefährdeten Testsuiten
   - genau zwei Teststeuerungsmaßnahmen

## Qualitätskontrolle vor der Ausgabe

Überprüfe vor der finalen Antwort:

- Wurden genau 15 Dateien pro Tag verarbeitet?
- Stimmen die Tagessummen mit den Suite-Level-Zahlen überein?
- Wurden die vorgegebenen Formeln korrekt angewendet?
- Stimmen alle Defect-IDs, Severity-Angaben und Statusangaben mit der Quelle überein?
- Wurden mehrdeutige Defect-Referenzen ausdrücklich gekennzeichnet?
- Wurden genau zwei Teststeuerungsmaßnahmen vorgeschlagen?
