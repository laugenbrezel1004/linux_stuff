# 🕵️‍♂️ Mission: Forensic Log-Cleanup

**Szenario:** Ein unbekannter Prozess hat dein System mit Logfiles überflutet. Dein Teamleiter vermutet, dass darin Spuren eines Angriffs versteckt sind. Bevor die Festplatte vollläuft, musst du die Beweise sichern (Archiv) und das System reinigen. Du hast genau 60 Minuten, bevor das System automatisch rebootet und alle Spuren löscht!

## 🛠 Teil 1: Die digitale Ausgrabungsstätte


Dein erster Auftrag: Rekonstruiere die Verzeichnisstruktur, in der der "Angreifer" gearbeitet hat.

1. Erstelle das Hauptquartier `~/logs` und das Sicherungsdepot `~/log_archive`.

2. Erstelle im Verzeichnis `~/logs` die Dateien `test`, `test.log`, `hallo.log`, `text.txt` sowie die Unterverzeichnis `blau` und `rot`.


## 🕰 Teil 2: Manipulation der Zeitlinie 


Der Angreifer hat versucht, seine Spuren zu verwischen, indem er Dateistempel geändert hat. Wir müssen das für unsere Analyse simulieren.

1. Versetze die Dateien `test`, `test.log` und das Verzeichnis `blau` künstlich in die Vergangenheit: Setze das Datum auf den 14. April 2024.

2. **Recherche-Check:** Welcher Flag bei touch erlaubt das Setzen eines exakten Zeitstempels? (Format: YYYYMMDDhhmm)

## 🔍 Teil 3: Die Nadel im Heuhaufen


Wir müssen die Logfiles mit "Inhalt" füllen, um die Suche zu testen.

1. Schleuse "Schadcode" ein:

   * Schreibe in `hallo.log` die Zeile: `INFO: System normal`.

   * Schreibe in `test.log` die Zeile: `KRITISCH: Unautorisierter Zugriff entdeckt!` 

2. **Filter-Task:** Nutze grep, um alle Dateien in `~/logs` zu finden, die auf `.log` enden und das Wort `KRITISCH` enthalten.

3. **Massen-Operation:** Kopiere alle Dateien, die mit "t" beginnen, in das Verzeichnis `rot`. Lösche sie dort sofort wieder – wir wollten nur sehen, ob dein Pattern-Matching funktioniert.

## 🚀 Teil 4: Die "Find"-Spezialoperation 


Jetzt wird es ernst. Die Festplatte ist zu 99% voll. Du musst alle alten Beweismittel (Dateien älter als 7 Tage) ins Archiv verschieben, um Platz zu schaffen.

Deine Aufgabe: Schreibe einen einzigen find-Befehl, der:

* Nur im Verzeichnis `~/logs` sucht.

* Nur echte Dateien (keine Verzeichnis!) findet.

* Nur Dateien mit der Endung `.log` berücksichtigt.

* Nur Dateien erfasst, die älter als 7 Tage sind.

* Diese Dateien automatisch nach `~/log_archive` verschiebt.

## 🏁 Teil 5: Forensic Report 


Überprüfe dein Werk mit `ls -l` in beiden Verzeichnissen.

* **Das Rätsel:** Warum wurde test.log archiviert, aber hallo.log blieb im aktiven Verzeichnis liegen?

* **Self-Check:** Was passiert, wenn du im find-Befehl den Typ -type f vergisst? 