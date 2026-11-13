# Eisschnelllauf – Wettkampf-Dashboard

Eine eigenständige, responsive Web-App zur Verwaltung und Auswertung eines Eisschnelllauf-Wettbewerbs mit 8 Teams.

## Funktionen

- 8 Teams mit je 5 aktiven Teilnehmern und 5 Ersatzläufern
- Import per Drag & Drop von CSV, TSV und Excel-Dateien (XLSX/XLS)
- Einfügen kopierter Excel-Tabellen per Copy & Paste
- Teilnehmerdaten direkt in der Tabelle bearbeiten
- Zwei Laufzeiten je Teilnehmer erfassen
- Automatische Addition der beiden Laufzeiten
- Teamwertung aus den drei schnellsten aktiven Teilnehmern
- Gesamtrangliste und Auszeichnungen für den schnellsten Jungen und das schnellste Mädchen
- Lokale Speicherung im Browser (localStorage); keine Teilnehmerdaten werden an einen Server gesendet

## Importformat

Die erste Tabellenzeile enthält Spaltenüberschriften. Unterstützte Spalten:

| Spalte | Pflicht | Beispiele |
|---|---|---|
| Team | empfohlen | Team 1, 1, Team Nord |
| Kategorie | empfohlen | Jungen, Mädchen |
| Vorname | ja | Max |
| Nachname | ja | Mustermann |
| Status | nein | Aktiv, Ersatz |

Ohne Status werden die ersten fünf Personen je Team als Aktiv und die nächsten fünf als Ersatz eingetragen. Pro Team werden maximal zehn Datensätze übernommen. Ein Import ersetzt die bisherige Teilnehmerliste und setzt Laufzeiten zurück.

## Zeitformat

Zeiten können als `42,35` (Sekunden) oder `0:42,35` (Minuten:Sekunden) eingegeben werden. Lauf 1 und Lauf 2 müssen vorhanden sein, damit eine Gesamtzeit gebildet wird.

## Lokal starten

Einfach `index.html` im Browser öffnen. Für den XLSX-Import wird bei Bedarf SheetJS über ein CDN geladen; CSV/TSV und Copy & Paste funktionieren ohne diese Bibliothek.

## GitHub Pages veröffentlichen

1. Im Repository **Settings → Pages** öffnen.
2. Unter **Build and deployment** als Quelle **Deploy from a branch** auswählen.
3. Branch **main** und Ordner **/(root)** auswählen und speichern.
4. Nach erfolgreicher Veröffentlichung ist die Website unter `https://vinzenz-hub.github.io/Eisschnellauf/` erreichbar.

Hinweis: GitHub Pages macht die veröffentlichte Website öffentlich erreichbar. Die importierten Teilnehmerdaten werden erst im Browser gespeichert und nicht in dieses Repository hochgeladen. Das Repository ist aktuell privat; die Verfügbarkeit von Pages für private Repositories hängt vom GitHub-Tarif ab.
