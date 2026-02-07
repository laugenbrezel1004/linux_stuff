## Aufgabe: Dateiberechtigungen lesen und ändern

Ziel: Rechte verstehen (`rwx` für User/Group/Others), mit `chmod` ändern und umask prüfen.

Vorbereitung:
- Erstelle den Ordner `rechte-demo` und darin die Datei `bericht.txt` mit beliebigem Inhalt.

Aufgaben:
1. Zeige die Rechte von `bericht.txt` in Langform an und identifiziere Besitzer und Gruppe.
   - Tipp: `ls -l`
2. Entferne das Ausführungsrecht für „others“ und füge Schreibrecht für die Gruppe hinzu.
   - Tipp: `chmod o-x,g+w bericht.txt`
3. Setze die Rechte exakt auf `rw-r-----` mithilfe der Oktalnotation.
   - Tipp: `chmod 640 bericht.txt`
4. Erzeuge eine neue Datei `neu.txt` und kontrolliere die Standardrechte. Erkläre, wie `umask` diese beeinflusst.
   - Tipp: `umask`, `touch neu.txt`
5. Setze im Ordner `rechte-demo` den Set-GID-Bit, sodass neue Dateien die Gruppen-ID erben. Erzeuge danach `team.txt` und prüfe die Gruppe.
   - Tipp: `chmod g+s rechte-demo`

Erwartung: Du kannst Rechte lesen, zielgerichtet ändern und den Einfluss von `umask` beschreiben.
