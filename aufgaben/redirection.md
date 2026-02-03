# 🛠️ Aufgabe: Linux Datenströme (I/O Redirection)

### Das Konzept von STDOUT und STDERR
In Linux produziert fast jeder Befehl zwei Arten von Ausgaben:
1.  **Standard Output (STDOUT):** Die normale, erfolgreiche Ausgabe des Programms (Dateideskriptor `1`).
2.  **Standard Error (STDERR):** Fehlermeldungen, wenn etwas nicht funktioniert (Dateideskriptor `2`).

Deine Aufgabe ist es, diese Ströme gezielt zu steuern und in Dateien zu schreiben.

---

## 🎯 Die Herausforderung
Führe die folgenden Operationen direkt in deiner Shell aus (oder schreibe die Befehle untereinander auf).

### 1. Nur die normale Ausgabe speichern
Führe einen Befehl aus, der eine Liste von Dateien anzeigt (z. B. `ls /etc`).
* **Ziel:** Schreibe die Liste in eine Datei namens `output.txt`.
* **Bedingung:** Eventuelle Fehlermeldungen dürfen **nicht** in der Datei landen, sondern müssen im Terminal sichtbar bleiben.

### 2. Nur die Fehlermeldungen abfangen
Versuche, ein Verzeichnis aufzulisten, auf das du keinen Zugriff hast oder das nicht existiert (z. B. `ls /root` oder `ls /dies/gibt/es/nicht`).
* **Ziel:** Die Fehlermeldung soll in eine Datei `errors.txt` geschrieben werden.
* **Bedingung:** Falls der Befehl doch etwas Erfolgreiches ausgibt, soll dies im Terminal erscheinen, nicht in der Datei.

### 3. Alles in eine Datei (Kombination)
Führe einen Befehl aus, der sowohl eine normale Ausgabe als auch einen Fehler provoziert.
* **Ziel:** Leite sowohl STDOUT als auch STDERR in eine einzige Datei namens `all_combined.log` um.
* **Anforderung:** Nutze den modernen Operator `&>`.

### 4. Daten anhängen statt überschreiben
Führe den ersten Befehl (`ls /etc`) erneut aus.
* **Ziel:** Die neue Ausgabe soll **unten** an die bereits existierende `output.txt` angehängt werden, ohne den alten Inhalt zu löschen.

### 5. Die "Stummschaltung" (Nirvana)
Führe einen beliebigen Befehl aus (z. B. `ping -c 3 google.com`).
* **Ziel:** Sorge dafür, dass **absolut keine** Ausgabe im Terminal erscheint (weder Erfolg noch Fehler).