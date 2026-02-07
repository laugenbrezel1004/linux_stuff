## Aufgabe: Wildcards und Globbing

Ziel: Dateien mithilfe von Mustern (`*`, `?`, `[]`) sicher adressieren.

Vorbereitung: Erzeuge den Ordner `wildcards-demo` und lege darin Dateien an:
```
notes.txt
notes-01.txt
notes-02.txt
bild-1.png
bild-2.png
bild-final.png
DATA_A.csv
DATA_B.csv
README
```

Aufgaben
1. Liste alle Textdateien auf, die mit `notes-` beginnen und zweistellige Nummern besitzen.
   - Erwartung: `notes-01.txt`, `notes-02.txt`
2. Liste alle PNGs mit einer einstelligen Zahl im Namen.
   - Erwartung: `bild-1.png`, `bild-2.png`
3. Liste alle CSV-Dateien, deren Suffix entweder `A` oder `B` ist.
   - Erwartung: `DATA_A.csv`, `DATA_B.csv`
4. Zeige nur Dateien an, die keinen Punkt im Namen haben.
   - Erwartung: `README`
5. Verschiebe alle `notes*.txt` in den Unterordner `texte/` (anlegen wenn nötig), ohne die anderen Dateien zu bewegen.

Tipp: Verwende `mkdir -p`, `ls`, `mv`, und die Glob-Muster `*`, `?`, `[AB]`, `[^.]`.
